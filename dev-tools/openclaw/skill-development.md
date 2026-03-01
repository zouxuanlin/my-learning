# OpenClaw 技能开发指南

> 文档更新时间：2026-03-01

## 什么是技能（Skills）

技能是 OpenClaw 中教导 AI 代理如何使用工具的教学文档。每个技能是一个目录，包含一个 `SKILL.md` 文件。

## 技能目录结构

```
my-skill/
├── SKILL.md          # 必需：技能说明文档
├── script.sh         # 可选：脚本文件
├── config.json       # 可选：配置文件
└── assets/           # 可选：资源文件
```

## SKILL.md 格式

### 基本结构

```markdown
---
name: my-skill-name
description: 技能的简短描述（用于技能列表）
metadata:
  {
    "openclaw": {
      "emoji": "🔧",
      "requires": { "bins": ["git"], "env": ["API_KEY"] },
      "primaryEnv": "API_KEY",
      "install": [
        {
          "kind": "brew",
          "formula": "my-tool",
          "bins": ["my-tool"],
          "label": "安装 My Tool"
        }
      ]
    }
  }
---

# 技能名称

## 功能描述

详细说明技能的功能和使用场景。

## 使用方法

### 命令格式

```
/skill-name [参数]
```

### 参数说明

- `param1` - 参数 1 的描述
- `param2` - 参数 2 的描述

## 示例

### 示例 1：基本用法

```bash
# 命令示例
skill-name arg1 arg2
```

### 示例 2：高级用法

```bash
# 带选项的命令
skill-name --option value
```

## 注意事项

- 安全提示
- 性能考虑
- 依赖要求

## 故障排除

常见问题和解决方案。
```

### Frontmatter 字段说明

| 字段 | 类型 | 必需 | 说明 |
|------|------|------|------|
| `name` | string | ✅ | 技能名称（唯一标识） |
| `description` | string | ✅ | 简短描述 |
| `metadata.openclaw.emoji` | string | ❌ | 显示图标 |
| `metadata.openclaw.homepage` | string | ❌ | 主页 URL |
| `metadata.openclaw.requires.bins` | array | ❌ | 需要的二进制文件 |
| `metadata.openclaw.requires.env` | array | ❌ | 需要的环境变量 |
| `metadata.openclaw.requires.config` | array | ❌ | 需要的配置项 |
| `metadata.openclaw.primaryEnv` | string | ❌ | 主要环境变量名 |
| `metadata.openclaw.install` | array | ❌ | 安装器配置 |
| `metadata.openclaw.os` | array | ❌ | 支持的操作系统 |
| `metadata.openclaw.always` | boolean | ❌ | 总是启用 |
| `user-invocable` | boolean | ❌ | 用户可调用（默认 true） |
| `disable-model-invocation` | boolean | ❌ | 禁用模型调用 |

### 安装器类型

#### Homebrew 安装器
```json
{
  "kind": "brew",
  "formula": "package-name",
  "bins": ["binary-name"],
  "label": "安装 Package Name",
  "os": ["darwin", "linux"]
}
```

#### Node.js 安装器
```json
{
  "kind": "node",
  "package": "@scope/package-name",
  "bins": ["command-name"],
  "label": "安装 Node Package"
}
```

#### Go 安装器
```json
{
  "kind": "go",
  "module": "github.com/user/repo",
  "bins": ["binary-name"],
  "label": "安装 Go Package"
}
```

#### UV/Python 安装器
```json
{
  "kind": "uv",
  "package": "package-name",
  "bins": ["script-name"],
  "label": "安装 Python Package"
}
```

#### 下载安装器
```json
{
  "kind": "download",
  "url": "https://example.com/tool.tar.gz",
  "archive": "tar.gz",
  "extract": true,
  "stripComponents": 1,
  "targetDir": "~/.openclaw/tools/",
  "bins": ["tool-binary"],
  "label": "下载并安装 Tool"
}
```

## 技能加载顺序

技能从三个位置加载，优先级从高到低：

1. **Workspace 技能**：`<workspace>/skills/`（最高优先级）
2. **本地技能**：`~/.openclaw/skills/`
3. **捆绑技能**：OpenClaw 内置技能（最低优先级）

### 配置额外技能目录

```json
{
  "skills": {
    "load": {
      "extraDirs": ["/path/to/shared/skills"]
    }
  }
}
```

## 技能配置

在 `~/.openclaw/openclaw.json` 中配置技能：

```json
{
  "skills": {
    "entries": {
      "my-skill": {
        "enabled": true,
        "apiKey": "YOUR_API_KEY",
        "env": {
          "CUSTOM_VAR": "value"
        },
        "config": {
          "customOption": "value"
        }
      }
    }
  }
}
```

### 密钥管理

#### 明文方式（不推荐）
```json
{
  "skills": {
    "entries": {
      "my-skill": {
        "apiKey": "sk-xxx-xxx-xxx"
      }
    }
  }
}
```

#### SecretRef 方式（推荐）
```json
{
  "skills": {
    "entries": {
      "my-skill": {
        "apiKey": {
          "source": "env",
          "provider": "default",
          "id": "MY_SKILL_API_KEY"
        }
      }
    }
  }
}
```

## 技能开发示例

### 示例 1：天气查询技能

```markdown
---
name: weather
description: 获取当前天气和预报（无需 API 密钥）
metadata:
  {
    "openclaw": {
      "emoji": "🌤️",
      "always": true
    }
  }
---

# 天气查询

## 功能

获取指定城市的当前天气和预报信息。

## 使用方法

### 查询当前天气
```
/weather [城市名]
```

### 查询预报
```
/weather [城市名] --forecast
```

## 示例

```bash
# 查询北京天气
/weather 北京

# 查询上海 3 天预报
/weather 上海 --forecast 3
```

## 输出格式

- 当前温度
- 天气状况
- 湿度
- 风速
- 预报（如请求）

## 注意事项

- 城市名支持中文和英文
- 预报最多支持 7 天
```

### 示例 2：GitHub 操作技能

```markdown
---
name: github-ops
description: GitHub 仓库操作技能
metadata:
  {
    "openclaw": {
      "emoji": "🐙",
      "requires": {
        "bins": ["gh"],
        "env": ["GITHUB_TOKEN"]
      },
      "primaryEnv": "GITHUB_TOKEN",
      "install": [
        {
          "kind": "brew",
          "formula": "gh",
          "bins": ["gh"],
          "label": "安装 GitHub CLI"
        }
      ]
    }
  }
---

# GitHub 操作

## 功能

通过 GitHub CLI 执行常见仓库操作。

## 前置条件

- 安装 GitHub CLI (`gh`)
- 设置 `GITHUB_TOKEN` 环境变量

## 使用方法

### 创建仓库
```
/github-ops create <repo-name> [--private]
```

### 克隆仓库
```
/github-ops clone <owner/repo>
```

### 创建 PR
```
/github-ops pr-create <title> [--body "description"]
```

### 查看 Issues
```
/github-ops issues list [--state open|closed|all]
```

## 示例

```bash
# 创建私有仓库
/github-ops create my-project --private

# 克隆仓库
/github-ops clone octocat/Hello-World

# 创建 PR
/github-ops pr-create "Fix bug" --body "This fixes the login issue"

# 查看开放 Issues
/github-ops issues list --state open
```

## 安全提示

- `GITHUB_TOKEN` 应仅授予最小必要权限
- 不要在日志中暴露 token
- 定期轮换 token
```

### 示例 3：网页搜索技能

```markdown
---
name: web-search
description: 使用 SearXNG 进行隐私网页搜索
metadata:
  {
    "openclaw": {
      "emoji": "🔍",
      "requires": {
        "config": ["searxng.enabled"]
      }
    }
  }
---

# 网页搜索

## 功能

使用本地 SearXNG 实例进行隐私保护的网页搜索。

## 配置

在 `~/.openclaw/openclaw.json` 中配置：

```json
{
  "tools": {
    "searxng": {
      "enabled": true,
      "instanceUrl": "http://localhost:8080"
    }
  }
}
```

## 使用方法

### 基本搜索
```
/search <查询词>
```

### 高级搜索
```
/search <查询词> --type web|image|news|video
/search <查询词> --limit 10
```

## 示例

```bash
# 搜索 OpenClaw 文档
/search OpenClaw documentation

# 搜索图片
/search cute cats --type image

# 搜索新闻
/search AI developments --type news --limit 5
```

## 输出格式

- 标题
- URL
- 摘要
- 来源

## 隐私说明

- 搜索请求通过本地 SearXNG 实例
- 不直接发送到外部搜索引擎
- 无搜索历史记录
```

## 技能测试

### 1. 语法检查

```bash
# 检查 SKILL.md 格式
cat skills/my-skill/SKILL.md | head -20
```

### 2. 加载测试

```bash
# 列出所有技能
openclaw skills list

# 查看特定技能
openclaw skills show my-skill
```

### 3. 功能测试

```bash
# 在聊天中测试
/skill-name test-args
```

## 技能发布

### 发布到 ClawHub

1. 创建技能仓库
2. 添加 SKILL.md 和相关文件
3. 提交到 ClawHub 注册表

### 版本管理

在 SKILL.md 中添加版本信息：

```markdown
---
name: my-skill
description: 技能描述
metadata:
  {
    "openclaw": {
      "version": "1.0.0",
      "changelog": "https://github.com/user/repo/releases"
    }
  }
---
```

## 最佳实践

### 1. 命名规范

- 使用小写字母和连字符
- 名称应简洁描述功能
- 避免与现有技能冲突

### 2. 文档质量

- 提供清晰的用法示例
- 说明所有参数和选项
- 包含故障排除部分

### 3. 安全考虑

- 最小权限原则
- 敏感信息使用 SecretRef
- 验证所有输入

### 4. 性能优化

- 缓存重复查询结果
- 限制输出大小
- 设置合理的超时

### 5. 错误处理

- 提供有意义的错误信息
- 优雅处理失败情况
- 记录关键错误

## 调试技巧

### 启用调试日志

```json
{
  "logging": {
    "level": "debug",
    "skills": true
  }
}
```

### 查看技能加载日志

```bash
openclaw gateway logs | grep -i skill
```

### 测试技能环境

```bash
# 检查二进制文件
which git
which gh

# 检查环境变量
echo $GITHUB_TOKEN
```

## 参考资源

- 官方技能文档：https://docs.openclaw.ai/tools/skills
- ClawHub：https://clawhub.com
- AgentSkills 规范：https://agentskills.io
- 示例技能：`/opt/openclaw/skills/`
