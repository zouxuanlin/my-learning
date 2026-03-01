# OpenClaw 配置指南

> 文档更新时间：2026-03-01

## 快速开始配置

### 1. 基础配置

配置文件位置：`~/.openclaw/openclaw.json`

```json
{
  "channels": {
    "telegram": {
      "botToken": "YOUR_BOT_TOKEN"
    }
  },
  "models": {
    "default": "anthropic/claude-sonnet-4-20250514"
  },
  "auth": {
    "entries": {
      "anthropic": {
        "apiKey": "YOUR_API_KEY"
      }
    }
  }
}
```

### 2. 通道配置

#### WhatsApp
```json
{
  "channels": {
    "whatsapp": {
      "allowFrom": ["+8613800138000"],
      "groups": {
        "*": { "requireMention": true }
      }
    }
  }
}
```

#### Telegram
```json
{
  "channels": {
    "telegram": {
      "botToken": "YOUR_BOT_TOKEN",
      "allowFrom": ["username1", "username2"]
    }
  }
}
```

#### Discord
```json
{
  "channels": {
    "discord": {
      "botToken": "YOUR_BOT_TOKEN",
      "allowFrom": ["user-id-1", "user-id-2"],
      "groups": {
        "*": { "requireMention": true }
      }
    }
  }
}
```

### 3. 工具配置

#### 编码配置文件
```json
{
  "tools": {
    "profile": "coding",
    "allow": ["group:fs", "group:runtime", "group:sessions"],
    "deny": ["browser"]
  }
}
```

#### 仅消息配置文件
```json
{
  "tools": {
    "profile": "messaging",
    "allow": ["telegram", "discord"]
  }
}
```

#### 最小配置文件
```json
{
  "tools": {
    "profile": "minimal"
  }
}
```

### 4. 多代理配置

```json
{
  "agents": {
    "list": [
      {
        "id": "main",
        "model": "anthropic/claude-sonnet-4-20250514",
        "tools": { "profile": "coding" }
      },
      {
        "id": "support",
        "model": "anthropic/claude-haiku-3-5",
        "tools": { "profile": "messaging" }
      },
      {
        "id": "researcher",
        "model": "anthropic/claude-sonnet-4-20250514",
        "tools": {
          "profile": "coding",
          "allow": ["group:web", "browser"]
        }
      }
    ]
  }
}
```

### 5. 技能配置

#### 启用/禁用技能
```json
{
  "skills": {
    "entries": {
      "weather": { "enabled": true },
      "searxng": { "enabled": true },
      "sag": { "enabled": false }
    }
  }
}
```

#### 技能环境变量
```json
{
  "skills": {
    "entries": {
      "gemini": {
        "enabled": true,
        "env": {
          "GEMINI_API_KEY": "YOUR_KEY_HERE"
        }
      }
    }
  }
}
```

### 6. Web 工具配置

```json
{
  "tools": {
    "web": {
      "search": {
        "enabled": true,
        "maxResults": 5
      },
      "fetch": {
        "enabled": true,
        "maxCharsCap": 50000
      }
    }
  },
  "auth": {
    "entries": {
      "brave": {
        "apiKey": "YOUR_BRAVE_API_KEY"
      }
    }
  }
}
```

### 7. 浏览器配置

```json
{
  "browser": {
    "enabled": true,
    "defaultProfile": "chrome",
    "profiles": {
      "chrome": {
        "port": 18800,
        "userDataDir": "~/.openclaw/browser/chrome"
      },
      "firefox": {
        "port": 18801,
        "userDataDir": "~/.openclaw/browser/firefox"
      }
    }
  }
}
```

### 8. 定时任务配置

```json
{
  "cron": {
    "jobs": [
      {
        "name": "daily-reminder",
        "schedule": {
          "kind": "cron",
          "expr": "0 9 * * *",
          "tz": "Asia/Shanghai"
        },
        "payload": {
          "kind": "agentTurn",
          "message": "发送每日提醒"
        },
        "sessionTarget": "isolated"
      },
      {
        "name": "hourly-check",
        "schedule": {
          "kind": "every",
          "everyMs": 3600000
        },
        "payload": {
          "kind": "systemEvent",
          "text": "HEARTBEAT"
        },
        "sessionTarget": "main"
      }
    ]
  }
}
```

### 9. 沙箱配置

```json
{
  "agents": {
    "defaults": {
      "sandbox": {
        "enabled": true,
        "docker": {
          "image": "node:22-alpine",
          "setupCommand": "apk add --no-cache git python3"
        }
      }
    }
  }
}
```

### 10. 环境变量配置

```bash
# ~/.openclaw/.env 或系统环境变量
OPENCLAW_HOME=/home/admin/.openclaw
OPENCLAW_STATE_DIR=/home/admin/.openclaw/state
OPENCLAW_CONFIG_PATH=/home/admin/.openclaw/openclaw.json

# API 密钥
ANTHROPIC_API_KEY=your_key_here
BRAVE_API_KEY=your_key_here
```

---

## 配置验证

### 检查配置语法
```bash
openclaw config get
```

### 测试通道连接
```bash
# WhatsApp
openclaw channels whatsapp status

# Telegram
openclaw channels telegram status

# Discord
openclaw channels discord status
```

### 查看工具状态
```bash
openclaw tools status
```

---

## 配置模板

### 个人开发者模板
```json
{
  "channels": {
    "telegram": {
      "botToken": "${TELEGRAM_BOT_TOKEN}"
    }
  },
  "models": {
    "default": "anthropic/claude-sonnet-4-20250514"
  },
  "auth": {
    "entries": {
      "anthropic": {
        "apiKey": "${ANTHROPIC_API_KEY}"
      }
    }
  },
  "tools": {
    "profile": "coding",
    "allow": ["group:fs", "group:runtime", "group:sessions", "group:web"]
  },
  "skills": {
    "entries": {
      "weather": { "enabled": true },
      "searxng": { "enabled": true }
    }
  }
}
```

### 团队协作文档
```json
{
  "channels": {
    "discord": {
      "botToken": "${DISCORD_BOT_TOKEN}",
      "allowFrom": ["user-id-1", "user-id-2", "user-id-3"],
      "groups": {
        "*": { "requireMention": true }
      }
    },
    "slack": {
      "botToken": "${SLACK_BOT_TOKEN}",
      "allowFrom": ["user-id-1", "user-id-2"]
    }
  },
  "tools": {
    "profile": "coding",
    "deny": ["browser"]
  },
  "agents": {
    "list": [
      {
        "id": "team-helper",
        "tools": { "profile": "coding" }
      }
    ]
  }
}
```

### 研究助手模板
```json
{
  "channels": {
    "whatsapp": {
      "allowFrom": ["+8613800138000"]
    }
  },
  "tools": {
    "profile": "coding",
    "allow": ["group:fs", "group:web", "browser", "group:sessions"]
  },
  "skills": {
    "entries": {
      "weather": { "enabled": true },
      "searxng": { "enabled": true },
      "healthcheck": { "enabled": true }
    }
  },
  "browser": {
    "enabled": true,
    "defaultProfile": "research"
  }
}
```

---

## 配置更新流程

### 1. 编辑配置
```bash
# 使用喜欢的编辑器
nano ~/.openclaw/openclaw.json
# 或
code ~/.openclaw/openclaw.json
```

### 2. 验证配置
```bash
openclaw config get
```

### 3. 应用配置
```bash
# 方法 1：使用 gateway 工具
openclaw gateway restart

# 方法 2：发送系统事件
# 配置会自动重载
```

### 4. 检查状态
```bash
openclaw status
openclaw gateway status
```

---

## 故障排除

### 配置无效
```bash
# 检查 JSON 语法
cat ~/.openclaw/openclaw.json | jq .

# 查看错误日志
openclaw gateway logs --follow
```

### 通道无法连接
1. 检查 API 密钥/Token 是否正确
2. 检查网络连接
3. 查看通道特定文档

### 技能不加载
1. 检查技能目录是否存在
2. 检查 SKILL.md 格式
3. 查看 `openclaw skills list`

### 工具不可用
1. 检查 `tools.allow` / `tools.deny` 配置
2. 检查技能是否启用
3. 查看工具状态

---

## 参考资源

- 完整配置 Schema：`openclaw config schema`
- 官方文档：https://docs.openclaw.ai/gateway/config
- 环境变量：https://docs.openclaw.ai/help/environment
