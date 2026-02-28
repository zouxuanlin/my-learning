# Claude CLI 中 Browser MCP 无法调用问题解决方案

## 问题描述

在项目中配置了 `.claude/mcp.json` 文件，但 Claude CLI 无法识别和调用 Browser MCP 服务器。

## 问题原因

Claude CLI 的 MCP 配置有以下层次结构：

1. **全局配置** - `~/.claude/mcp.json`（对所有项目生效）
2. **项目本地配置** - 存储在 `~/.claude/projects/{project-path}/mcp.json`（通过 CLI 命令添加）
3. **项目目录配置** - `.claude/mcp.json`（在项目根目录下）

**关键发现**：Claude CLI 优先读取通过 `claude mcp` 命令管理的项目本地配置，而不是项目目录中的 `.claude/mcp.json` 文件。

## 解决方案

### 方法一：使用 CLI 命令添加（推荐）

在项目目录下，使用 `claude mcp add-json` 命令添加 MCP 服务器：

```bash
# 进入项目目录
cd /path/to/your/project

# 添加 Browser MCP
claude mcp add-json --scope local browsermcp '{"command":"npx","args":["-y","@browsermcp/mcp"]}'

# 验证配置
claude mcp list
```

### 方法二：手动编辑配置文件

直接编辑项目级别的 MCP 配置文件：

**配置文件路径**：`~/.claude/projects/{project-path}/mcp.json`

其中 `{project-path}` 是将项目路径的 `/` 替换为 `-` 的字符串。

**配置示例**：

```json
{
  "mcpServers": {
    "browsermcp": {
      "command": "npx",
      "args": ["-y", "@browsermcp/mcp"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your_token_here"
      }
    }
  }
}
```

## 验证配置

### 1. 列出所有 MCP 服务器

```bash
unset CLAUDECODE && claude mcp list
```

输出示例：
```
Checking MCP server health...

github: https://api.githubcopilot.com/mcp (HTTP) - ✓ Connected
browsermcp: npx -y @browsermcp/mcp - ✓ Connected
```

### 2. 查看特定 MCP 服务器配置

```bash
unset CLAUDECODE && claude mcp get browsermcp
```

输出示例：
```
browsermcp:
  Scope: Local config (private to you in this project)
  Status: ✓ Connected
```

## 常用 CLI 命令

```bash
# 列出所有 MCP 服务器
claude mcp list

# 添加 MCP 服务器（JSON 配置）
claude mcp add-json --scope local <name> '<json-config>'

# 添加 MCP 服务器（交互式）
claude mcp add <name> -- npx <package-name>

# 获取 MCP 服务器详情
claude mcp get <name>

# 移除 MCP 服务器
claude mcp remove <name> -s local

# 重置项目中的 MCP 选择
claude mcp reset-project-choices
```

## Browser MCP 配置示例

```json
{
  "mcpServers": {
    "browsermcp": {
      "command": "npx",
      "args": ["-y", "@browsermcp/mcp"]
    }
  }
}
```

## 注意事项

1. **环境变量**：在 Claude CLI 内运行命令时，可能需要 `unset CLAUDECODE` 来避免嵌套会话错误

2. **配置作用域**：
   - `--scope local` - 仅对当前项目生效
   - `--scope global` - 对所有项目生效

3. **Browser MCP 已知问题**：`@browsermcp/mcp` 包在关闭时有一个已知的递归调用 bug，但不影响正常使用

4. **配置文件同步**：项目目录下的 `.claude/mcp.json` 不会自动同步到 Claude CLI 的配置系统中，需要使用 CLI 命令添加

## 参考资料

- [Browser MCP 文档](https://docs.browsermcp.io/)
- [Claude Code MCP 配置指南](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/mcp)
