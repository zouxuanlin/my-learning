# macOS Zsh 拷贝命令执行卡顿解决方案

## 问题现象

在 macOS 终端中，从其他地方拷贝命令到 zsh 执行时，会出现明显的卡顿现象，命令需要等待很久才能执行。

## 问题原因

### 1. Bracketed Paste 模式（主要原因）

macOS Catalina 及之后版本默认使用 zsh，而 zsh 启用了 **bracketed paste**（括号粘贴）模式。这个模式的目的是：
- 区分手动输入和粘贴的文本
- 防止粘贴恶意代码
- 在粘贴多行文本时提供保护

但对于频繁的拷贝粘贴操作，这个模式会导致明显的延迟。

### 2. Oh-My-Zsh 插件问题（次要原因）

- 加载了不存在的插件（如 `incr`）会导致每次启动时查找失败
- 过多插件会拖慢 shell 启动速度
- 重复 source 插件文件

## 解决方案

### 方案一：禁用 Bracketed Paste（推荐）

在 `~/.zshrc` 文件中添加以下配置：

```bash
# 在 oh-my-zsh 加载前设置
DISABLE_MAGIC_FUNCTIONS="true"

source $ZSH/oh-my-zsh.sh
```

### 方案二：优化 Oh-My-Zsh 插件

1. 检查并移除不存在的插件：

```bash
# 编辑 ~/.zshrc
plugins=(
    git
    # 移除不存在的插件，如 incr
)
```

2. 安装常用且有效的插件：

```bash
# 安装 zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# 安装 zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

3. 更新插件配置：

```bash
plugins=(
    git
    zsh-autosuggestions
    zsh-syntax-highlighting
)
```

### 方案三：清理重复配置

检查 `~/.zshrc` 文件，移除重复的配置项：
- 重复的 `source` 语句
- 重复的 `export` 语句
- 无效的别名定义

## 验证修复效果

### 测试 zsh 启动时间

```bash
time zsh -i -c 'echo test'
```

**修复前**：约 2.4 秒
**修复后**：约 0.25 秒

## 完整配置示例

```bash
# Path to your oh-my-zsh installation.
export ZSH="/Users/yourname/.oh-my-zsh"

# 使用固定主题，避免 random 主题的额外加载时间
ZSH_THEME="robbyrussell"

# 禁用魔术函数，解决拷贝粘贴卡顿
DISABLE_MAGIC_FUNCTIONS="true"

# 插件配置 - 只使用有效且必要的插件
plugins=(
    git
    zsh-autosuggestions
    zsh-syntax-highlighting
)

source $ZSH/oh-my-zsh.sh

# 个人配置
alias ll="ls -la"
alias s="cd .."
alias ss="cd ../.."
```

## 其他优化建议

### 1. 禁用自动更新检查

```bash
export DISABLE_AUTO_UPDATE="true"
```

### 2. 使用固定主题

`random` 主题每次启动都会随机加载一个主题，会增加启动时间。建议使用固定主题。

## 参考链接

- [Oh-My-Zsh 官方文档](https://ohmyz.sh/)
- [zsh-users/zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
- [zsh-users/zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
- [Understanding Bracketed Paste in Zsh](https://cirw.in/blog/bracketed-paste)
