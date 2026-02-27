# GitHub MCP Server 集成指南

Model Context Protocol (MCP) 是一个开放协议，允许 AI 助手（如 Claude Code）与外部服务（如 GitHub）安全交互。GitHub 官方提供了 MCP 服务器实现。

---

## 目录

1. [什么是 MCP](#什么是-mcp)
2. [安装 GitHub MCP Server](#安装-github-mcp-server)
3. [配置 Claude Code](#配置-claude-code)
4. [可用工具列表](#可用工具列表)
5. [使用示例](#使用示例)
6. [故障排除](#故障排除)

---

## 什么是 MCP

MCP (Model Context Protocol) 是一个标准化协议，用于连接 AI 模型与外部数据源和工具。通过 MCP，Claude Code 可以：

- 安全地访问 GitHub API
- 执行仓库管理、Issue 处理、PR 审查等操作
- 无需在代码中硬编码 API token

---

## 安装 GitHub MCP Server

### 前置要求

- Node.js 18+ 或 `uv` 包管理器
- GitHub Personal Access Token (推荐 fine-grained token)
- Claude Code CLI

### 获取 GitHub Token

1. 访问 https://github.com/settings/tokens
2. 创建新的 **fine-grained token** 或 **classic token**
3. 推荐权限（fine-grained）：
   - `Contents`: Read (读取仓库代码)
   - `Issues`: Read/Write (管理 Issues)
   - `Pull requests`: Read/Write (管理 PR)
   - `Metadata`: Read (只读访问基本信息)
4. 复制生成的 token，后续配置使用

### 安装方式

#### 方式一：使用 npx (推荐)

```bash
# 无需全局安装，直接通过 npx 运行
npx -y @modelcontextprotocol/server-github
```

#### 方式二：全局安装

```bash
npm install -g @modelcontextprotocol/server-github
```

#### 方式三：使用 uv (Python 生态)

```bash
uvx mcp-server-github
```

#### 方式四：Docker

```bash
docker pull mcp/github-server
```

---

## 配置 Claude Code

### 配置文件位置

| 系统 | 配置文件路径 |
|------|-------------|
| macOS | `~/.config/claude-code/config.json` |
| Linux | `~/.config/claude-code/config.json` |
| Windows | `%APPDATA%\Claude-Code\config.json` |

### 配置步骤

1. **创建/编辑配置文件**

```bash
# macOS/Linux
mkdir -p ~/.config/claude-code
code ~/.config/claude-code/config.json
```

2. **添加 MCP Server 配置**

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "YOUR_GITHUB_TOKEN_HERE"
      }
    }
  }
}
```

3. **使用 Docker 的配置方式（可选）**

```json
{
  "mcpServers": {
    "github": {
      "command": "docker",
      "args": ["run", "-i", "--rm", "-e", "GITHUB_PERSONAL_ACCESS_TOKEN", "mcp/github-server"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "YOUR_GITHUB_TOKEN_HERE"
      }
    }
  }
}
```

4. **验证配置**

启动 Claude Code 后，可以通过以下方式验证 MCP 是否工作：

```
/mcp
```

查看已连接的服务器和可用工具。

---

## 可用工具列表

GitHub MCP Server 提供以下工具：

### 仓库操作

| 工具 | 描述 |
|------|------|
| `github-read_repository` | 读取仓库详细信息 |
| `github-search_repositories` | 搜索仓库 |
| `github-list_commits` | 列出提交历史 |
| `github-get_file_contents` | 获取文件内容 |
| `github-push_files` | 推送文件到仓库 |
| `github-create_branch` | 创建分支 |
| `github-create_repository` | 创建新仓库 |

### Issue 管理

| 工具 | 描述 |
|------|------|
| `github-get_issue` | 获取 Issue 详情 |
| `github-create_issue` | 创建新 Issue |
| `github-update_issue` | 更新 Issue |
| `github-list_issues` | 列出 Issues |
| `github-add_issue_comment` | 添加 Issue 评论 |

### Pull Request

| 工具 | 描述 |
|------|------|
| `github-get_pull_request` | 获取 PR 详情 |
| `github-create_pull_request` | 创建新 PR |
| `github-update_pull_request` | 更新 PR |
| `github-list_pull_requests` | 列出 PRs |
| `github-merge_pull_request` | 合并 PR |
| `github-get_pull_request_files` | 获取 PR 修改的文件 |
| `github-get_pull_request_comments` | 获取 PR 评论 |
| `github-get_pull_request_reviews` | 获取 PR 审查 |

### 其他

| 工具 | 描述 |
|------|------|
| `github-fork_repository` | Fork 仓库 |
| `github-create_gist` | 创建 Gist |
| `github-search_code` | 搜索代码 |
| `github-search_users` | 搜索用户 |
| `github-get_code_scanning_alert` | 获取代码扫描告警 |

---

## 使用示例

### 示例 1：读取仓库信息

```
请帮我读取 github.com/anthropics/claude-code 仓库的基本信息
```

### 示例 2：创建 Issue

```
在仓库 {owner}/{repo} 创建一个新的 Issue，标题是 "Bug: xxx"，描述问题详情...
```

### 示例 3：审查 Pull Request

```
帮我审查这个 PR：https://github.com/{owner}/{repo}/pull/{number}
列出所有修改的文件，并总结变更内容
```

### 示例 4：搜索相关 Issue

```
搜索仓库中标签为 "bug" 且状态为 "open" 的 Issues
```

### 示例 5：获取文件内容

```
读取仓库 main 分支中 src/index.ts 的内容
```

---

## 故障排除

### 问题 1：MCP Server 未连接

**症状**：`/mcp` 命令显示无服务器

**解决方案**：
1. 检查配置文件路径是否正确
2. 检查 JSON 格式是否正确（可使用 `jq` 或在线 JSON 验证器）
3. 重启 Claude Code

### 问题 2：Token 无效

**症状**：API 调用返回 401 错误

**解决方案**：
1. 确认 token 已正确复制到配置中
2. 检查 token 是否过期
3. 确认 token 权限是否足够

### 问题 3：npx 命令找不到

**症状**：提示 `command not found: npx`

**解决方案**：
1. 安装 Node.js (https://nodejs.org)
2. 或使用 Docker 方式运行
3. 或改用 uv 方式

### 问题 4：速率限制

**症状**：API 调用返回 403 rate limit

**解决方案**：
1. 使用 fine-grained token 而非 classic token
2. 等待速率限制重置（通常 1 小时）
3. 考虑升级到 GitHub Pro

---

## 参考资源

- [GitHub MCP Server 官方仓库](https://github.com/modelcontextprotocol/servers)
- [MCP 官方文档](https://modelcontextprotocol.io/)
- [Claude Code MCP 文档](https://claude.ai/code/docs)
- [Smithery - MCP 服务器目录](https://smithery.ai/)

---

*最后更新：2026-02-27*
