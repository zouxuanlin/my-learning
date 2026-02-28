# GitHub MCP 连接失败问题解决方案

## 问题描述

GitHub MCP Server 连接失败，无法正常使用 GitHub 相关功能。

## 问题诊断

### 1. 检查当前配置

查看 Claude Code 的 MCP 配置文件：

```bash
cat ~/.config/claude-code/config.json
```

当前配置：
```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "$GITHUB_TOKEN"
      }
    }
  }
}
```

### 2. 问题根因

配置文件中 `"GITHUB_PERSONAL_ACCESS_TOKEN": "$GITHUB_TOKEN"` 使用的是**字面字符串** `$GITHUB_TOKEN`，而不是实际的环境变量值。

JSON 配置文件不会自动展开 shell 环境变量，因此 MCP Server 收到的是无效 token。

### 3. 验证 gh 登录状态

```bash
gh auth status
```

输出示例：
```
github.com
  ✓ Logged in to github.com account zouxuanlin (keyring)
  - Active account: true
  - Git operations protocol: https
  - Token: gho_************************************
  - Token scopes: 'gist', 'read:org', 'repo', 'workflow'
```

## 解决方案

### 方案一：使用 gh CLI 动态获取 Token（推荐）

修改配置文件，使用命令替换方式获取 token：

**不适用** - JSON 不支持命令替换。

正确做法：创建一个 wrapper 脚本或使用以下方式。

### 方案二：直接配置 Token 值

1. 获取当前 gh 的 token：
```bash
gh auth token
```

2. 编辑配置文件：
```bash
code ~/.config/claude-code/config.json
```

3. 将 token 值直接填入：
```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "gho_your_actual_token_here"
      }
    }
  }
}
```

### 方案三：使用环境变量文件

1. 在 `~/.config/claude-code/` 创建 `.env` 文件：
```bash
echo "GITHUB_PERSONAL_ACCESS_TOKEN=$(gh auth token)" > ~/.config/claude-code/.env
```

2. 修改配置文件引用（需要 Claude Code 支持.env 加载）。

### 方案四：设置全局环境变量（不推荐）

在 `~/.zshrc` 中添加：
```bash
export GITHUB_TOKEN=$(gh auth token)
```

然后重新加载：
```bash
source ~/.zshrc
```

**注意**：这种方式可能导致 token 过期后失效，需要定期更新。

## 推荐的最终配置

考虑到使用 gh CLI 的管理方式，最佳方案是**直接使用 gh auth token 获取 token 并配置到 config.json**。

### 快速修复步骤

```bash
# 1. 获取 token
TOKEN=$(gh auth token)

# 2. 备份原配置
cp ~/.config/claude-code/config.json ~/.config/claude-code/config.json.bak

# 3. 更新配置（使用 jq 或手动编辑）
cat > ~/.config/claude-code/config.json << EOF
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "$TOKEN"
      }
    }
  }
}
EOF

# 4. 验证配置
cat ~/.config/claude-code/config.json

# 5. 重启 Claude Code 并测试
```

## 验证修复

### 测试步骤

1. **测试 MCP Server 启动**
```bash
# 直接使用 npx 测试 GitHub MCP Server
GITHUB_PERSONAL_ACCESS_TOKEN="your_token" npx -y @modelcontextprotocol/server-github
```

2. **测试 MCP 初始化**
发送 JSON-RPC 初始化请求：
```json
{"jsonrpc":"2.0","method":"initialize","params":{"protocolVersion":"2024-11-05","capabilities":{},"clientInfo":{"name":"test","version":"1.0"}},"id":1}
```

期望响应：
```json
{"result":{"protocolVersion":"2024-11-05","capabilities":{"tools":{}},"serverInfo":{"name":"github-mcp-server","version":"0.6.2"}},"jsonrpc":"2.0","id":1}
```

3. **测试工具列表**
```json
{"jsonrpc":"2.0","method":"tools/list","params":{},"id":2}
```

### 测试结果

测试通过！MCP Server 成功响应并返回可用工具列表：

- `create_or_update_file` - 创建/更新文件
- `search_repositories` - 搜索仓库
- `create_repository` - 创建仓库
- `get_file_contents` - 获取文件内容
- `push_files` - 推送多个文件
- `create_issue` - 创建 Issue
- `create_pull_request` - 创建 PR
- `fork_repository` - Fork 仓库
- `create_branch` - 创建分支
- `list_commits` - 列出提交
- `list_issues` - 列出 Issues
- `update_issue` - 更新 Issue
- `add_issue_comment` - 添加评论
- `search_code` - 搜索代码
- `search_issues` - 搜索 Issues
- `search_users` - 搜索用户
- `get_issue` - 获取 Issue 详情
- `get_pull_request` - 获取 PR 详情
- `list_pull_requests` - 列出 PRs
- `create_pull_request_review` - 创建 PR 审查
- `merge_pull_request` - 合并 PR
- `get_pull_request_files` - 获取 PR 修改文件
- `get_pull_request_status` - 获取 PR 状态
- `update_pull_request_branch` - 更新 PR 分支
- `get_pull_request_comments` - 获取 PR 评论
- `get_pull_request_reviews` - 获取 PR 审查

### 在 Claude Code 中使用

1. 启动 Claude Code
2. 运行 `/mcp` 命令查看已连接的服务器
3. 尝试使用 GitHub 相关功能，如：
   ```
   帮我读取 github.com/zouxuanlin/my-learning 仓库的信息
   ```

## Token 过期处理

如果日后遇到 token 过期问题：

1. 刷新 token（gh 会自动管理）：
```bash
gh auth refresh
```

2. 重新获取 token 并更新配置：
```bash
TOKEN=$(gh auth token)
# 重复上述配置步骤
```

## 相关资源

- [GitHub CLI 文档](https://cli.github.com/)
- [GitHub MCP Server 文档](https://github.com/modelcontextprotocol/servers)
- [Claude Code MCP 配置](../claude-code-mcp-skills-guide.md)

---

*创建日期：2026-02-28*
*问题类型：配置错误 - 环境变量未正确展开*
