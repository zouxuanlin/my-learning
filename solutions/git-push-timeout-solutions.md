# Git Push 超时问题解决方案

## 问题描述
`git push` 命令超时，错误信息：
```
fatal: unable to access 'https://github.com/...': Failed to connect to github.com port 443 after 75007 ms: Couldn't connect to server
```

## 根本原因
网络连接问题导致无法连接到 GitHub 的 HTTPS 服务（端口 443）。

## 解决方案

### 1. 检查网络连接
```bash
# 测试 GitHub 连通性
ping github.com

# 测试 HTTPS 端口
nc -zv github.com 443

# 测试 curl 访问
curl -I https://github.com
```

### 2. 配置 Git 代理（如有需要）
如果你在使用代理：

```bash
# 设置 HTTP 代理
git config --global http.proxy http://proxy.example.com:8080
git config --global https.proxy https://proxy.example.com:8080

# 取消代理设置
git config --global --unset http.proxy
git config --global --unset https.proxy
```

### 3. 增加 Git 超时时间
```bash
# 设置更长的超时时间（单位：秒）
git config --global http.postBuffer 524288000  # 500MB
git config --global http.lowSpeedLimit 0
git config --global http.lowSpeedTime 999999   # 超时时间
```

### 4. 使用 SSH 替代 HTTPS
SSH 连接通常更稳定：

#### 步骤 1: 生成 SSH 密钥（如尚未生成）
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

#### 步骤 2: 添加 SSH 密钥到 GitHub
```bash
# 复制公钥
cat ~/.ssh/id_ed25519.pub

# 添加到 GitHub: Settings → SSH and GPG keys → New SSH key
```

#### 步骤 3: 更改远程仓库 URL
```bash
# 查看当前远程仓库
git remote -v

# 更改为 SSH URL
git remote set-url origin git@github.com:zouxuanlin/my-learning.git

# 验证更改
git remote -v
```

#### 步骤 4: 测试 SSH 连接
```bash
ssh -T git@github.com
```

### 5. 使用 GitHub CLI 推送
GitHub CLI (`gh`) 可能使用不同的网络配置：

```bash
# 使用 gh 推送
gh repo sync

# 或者直接推送当前分支
gh pr create --fill  # 创建 Pull Request
```

### 6. 分块推送大文件
如果仓库中有大文件：

```bash
# 使用 Git LFS（大文件存储）
git lfs install
git lfs track "*.psd"
git add .gitattributes
git commit -m "Add LFS tracking"
git push origin master
```

### 7. 使用 Git 深度克隆和浅推送
```bash
# 如果历史记录很深，可以浅推送
git push --depth=1 origin master

# 或者推送单个提交
git push origin HEAD
```

### 8. 检查防火墙和安全软件
- 检查 macOS 防火墙设置
- 暂时禁用安全软件
- 检查 VPN 连接

### 9. 更改 DNS 服务器
有时 DNS 解析问题：

```bash
# 临时使用 Google DNS
sudo networksetup -setdnsservers Wi-Fi 8.8.8.8 8.8.4.4

# 重置为自动获取
sudo networksetup -setdnsservers Wi-Fi empty
```

### 10. 使用 Git 的调试模式
查看详细错误信息：

```bash
GIT_TRACE=1 GIT_CURL_VERBOSE=1 git push origin master
```

## 快速测试脚本
创建一个测试脚本检查连接：

```bash
#!/bin/bash
echo "=== GitHub 连接测试 ==="
echo "1. 测试 ping..."
ping -c 3 github.com
echo -e "\n2. 测试端口 443..."
nc -zv github.com 443
echo -e "\n3. 测试 HTTPS 访问..."
curl -I --connect-timeout 10 https://github.com
echo -e "\n4. 测试 SSH 访问..."
ssh -T -o ConnectTimeout=5 git@github.com
```

## 备选方案
如果上述方法都无效：

1. **使用 GitHub Desktop 客户端**
2. **通过 VPN 连接**
3. **在另一网络环境中尝试（如手机热点）**
4. **使用 `git bundle` 离线打包**
   ```bash
   git bundle create repo.bundle master
   # 在其他地方解包
   git clone repo.bundle my-learning
   ```

## 验证解决
成功推送后验证：

```bash
# 检查远程分支
git branch -r

# 查看 GitHub 仓库
gh repo view --web

# 查看提交历史
git log --oneline --all --graph
```

## 联系支持
如果问题持续存在：
- GitHub 状态页：https://www.githubstatus.com/
- GitHub 支持：https://support.github.com/