# MCP 配置示例

本目录包含各种 MCP 服务器的配置示例，可以直接复制使用。

---

## 配置位置

- **macOS/Linux**: `~/.config/claude-code/config.json`
- **Windows**: `%APPDATA%\Claude-Code\config.json`

---

## GitHub MCP 配置

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "YOUR_TOKEN_HERE"
      }
    }
  }
}
```

**获取 Token 步骤**：
1. 访问 https://github.com/settings/tokens
2. 创建 fine-grained token
3. 选择需要的权限（Contents: Read, Issues: Read/Write, Pull requests: Read/Write）
4. 复制 token 到配置中

---

## PostgreSQL MCP 配置

```json
{
  "mcpServers": {
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres"],
      "env": {
        "DATABASE_URL": "postgresql://user:password@localhost:5432/database"
      }
    }
  }
}
```

---

## SQLite MCP 配置

```json
{
  "mcpServers": {
    "sqlite": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sqlite"],
      "env": {
        "SQLITE_DB_PATH": "/path/to/your/database.db"
      }
    }
  }
}
```

---

## Filesystem MCP 配置

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "ALLOWED_DIRECTORIES": "/Users/username/projects,/Users/username/docs"
      }
    }
  }
}
```

---

## Memory MCP 配置

```json
{
  "mcpServers": {
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    }
  }
}
```

Memory 服务器不需要额外的环境变量，它会在本地创建数据库。

---

## Slack MCP 配置

```json
{
  "mcpServers": {
    "slack": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-slack"],
      "env": {
        "SLACK_BOT_TOKEN": "xoxb-your-bot-token",
        "SLACK_TEAM_ID": "T01234567"
      }
    }
  }
}
```

---

## 多个 MCP 服务器配置示例

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "YOUR_TOKEN"
      }
    },
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres"],
      "env": {
        "DATABASE_URL": "postgresql://localhost:5432/mydb"
      }
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    }
  }
}
```

---

## 使用 uv 方式配置

如果你使用 Python/uv 生态：

```json
{
  "mcpServers": {
    "github": {
      "command": "uvx",
      "args": ["mcp-server-github"],
      "env": {
        "GITHUB_TOKEN": "YOUR_TOKEN"
      }
    }
  }
}
```

---

## 使用 Docker 方式配置

```json
{
  "mcpServers": {
    "github": {
      "command": "docker",
      "args": ["run", "-i", "--rm", "-e", "GITHUB_PERSONAL_ACCESS_TOKEN", "mcp/github-server"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "YOUR_TOKEN"
      }
    }
  }
}
```

---

## 安全建议

1. **不要将 token 硬编码在配置文件中**，可以使用环境变量引用：
   ```bash
   # 在 ~/.zshrc 或 ~/.bashrc 中添加
   export GITHUB_TOKEN="your-token"
   ```

   ```json
   // config.json 中引用
   {
     "mcpServers": {
       "github": {
         "env": {
           "GITHUB_PERSONAL_ACCESS_TOKEN": "$GITHUB_TOKEN"
         }
       }
     }
   }
   ```

2. **使用 fine-grained token** 而非 classic token，遵循最小权限原则

3. **定期轮换 token**，避免长期使用同一个 token

---

*最后更新：2026-02-28*
