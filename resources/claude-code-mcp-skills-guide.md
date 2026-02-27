# Claude Code 中 MCP 与 Skills 组织方式指南

本文档详细介绍 Claude Code 中 MCP (Model Context Protocol) 和 Skills 的组织方式、配置方法及最佳实践。

---

## 目录

1. [MCP (Model Context Protocol)](#1-mcp-model-context-protocol)
2. [Skills 系统](#2-skills-系统)
3. [配置文件结构](#3-配置文件结构)
4. [组织方式与最佳实践](#4-组织方式与最佳实践)

---

## 1. MCP (Model Context Protocol)

### 1.1 什么是 MCP

MCP 是一个开放协议，允许 AI 助手（如 Claude Code）与外部服务安全交互。通过 MCP，Claude Code 可以：

- 安全地访问外部 API（如 GitHub、Slack、数据库等）
- 执行各种操作而无需在代码中硬编码凭证
- 通过标准化协议连接不同的数据源和工具

### 1.2 MCP 架构

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   Claude Code   │────▶│  MCP 配置层     │────▶│  MCP Server     │
│   (AI 客户端)    │     │  (config.json)  │     │  (外部服务)     │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

### 1.3 MCP 服务器配置

**配置文件位置**：

| 系统 | 配置文件路径 |
|------|-------------|
| macOS | `~/.config/claude-code/config.json` |
| Linux | `~/.config/claude-code/config.json` |
| Windows | `%APPDATA%\Claude-Code\config.json` |

**基本配置格式**：

```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-name"],
      "env": {
        "API_KEY": "your-api-key"
      }
    }
  }
}
```

### 1.4 常用 MCP 服务器

| 服务器 | 描述 | 安装方式 |
|--------|------|----------|
| GitHub | GitHub API 集成 | `npx -y @modelcontextprotocol/server-github` |
| PostgreSQL | PostgreSQL 数据库操作 | `npx -y @modelcontextprotocol/server-postgres` |
| Slack | Slack 消息发送与管理 | `npx -y @modelcontextprotocol/server-slack` |
| Filesystem | 文件系统操作 | `npx -y @modelcontextprotocol/server-filesystem` |
| Memory | 持久化记忆存储 | `npx -y @modelcontextprotocol/server-memory` |

### 1.5 完整配置示例

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
        "DATABASE_URL": "postgresql://user:password@localhost:5432/dbname"
      }
    }
  }
}
```

### 1.6 MCP 可用命令

在 Claude Code 中，使用 `/mcp` 命令可以：
- 查看已连接的 MCP 服务器
- 列出每个服务器提供的工具
- 调试 MCP 连接问题

---

## 2. Skills 系统

### 2.1 什么是 Skills

Skills 是 Claude Code 中的技能系统，允许用户通过特定命令（如 `/commit`、`/review-pr`）触发预定义的工作流程。

**技能类型**：
- **系统内置技能**：如 `/help`、`/clear`、`/mcp`
- **用户自定义技能**：通过 CLAUDE.md 或 skills 配置定义
- **文档技能 (document-skills)**：用于处理特定文档类型的技能

### 2.2 常用内置 Skills

| 命令 | 描述 |
|------|------|
| `/help` | 获取帮助信息 |
| `/clear` | 清除当前对话上下文 |
| `/mcp` | 管理 MCP 服务器连接 |
| `/commit` | 创建 git 提交 |
| `/review-pr` | 审查 Pull Request |

### 2.3 文档 Skills (document-skills)

文档技能是一类特殊的技能，用于处理特定类型的文档和任务：

#### 创作类技能

| 技能 | 用途 |
|------|------|
| `docx` | 创建、编辑 Word 文档 (.docx) |
| `pdf` | 读取、创建、编辑 PDF 文件 |
| `pptx` | 创建、编辑 PowerPoint 演示文稿 |
| `xlsx` | 处理 Excel 电子表格 (.xlsx, .csv) |

#### 设计类技能

| 技能 | 用途 |
|------|------|
| `frontend-design` | 创建高质量前端界面 |
| `canvas-design` | 创建静态视觉设计 (.png, .pdf) |
| `brand-guidelines` | 应用品牌视觉规范 |
| `theme-factory` | 为 artifacts 应用主题样式 |

#### 专业类技能

| 技能 | 用途 |
|------|------|
| `mcp-builder` | 创建 MCP 服务器 |
| `web-artifacts-builder` | 创建复杂多组件 HTML artifacts |
| `webapp-testing` | 使用 Playwright 测试 Web 应用 |
| `algorithmic-art` | 使用 p5.js 创建算法艺术 |
| `slack-gif-creator` | 为 Slack 创建动画 GIF |

#### 沟通类技能

| 技能 | 用途 |
|------|------|
| `internal-comms` | 撰写内部沟通文档（状态报告、领导更新等） |
| `doc-coauthoring` | 协作文档创作工作流 |
| `skill-creator` | 创建新的 skills |

### 2.4 如何使用 Skills

技能使用斜杠命令语法：

```
/<skill-name> [参数]
```

例如：
```
/commit -m "修复登录 bug"
/review-pr 123
```

---

## 3. 配置文件结构

### 3.1 全局配置 (config.json)

位置：`~/.config/claude-code/config.json`

```json
{
  "mcpServers": {
    // MCP 服务器配置
  },
  "permissions": {
    // 权限配置
  }
}
```

### 3.2 项目配置 (CLAUDE.md)

每个项目可以有 `CLAUDE.md` 文件，提供项目特定的指导：

```markdown
# CLAUDE.md

## 项目概述
简要描述项目

## 目录结构
说明项目目录组织

## 开发规范
编码规范、测试要求等

## 常用命令
项目特定的命令或脚本
```

### 3.3 项目设置 (.claude/)

项目级别的 `.claude` 目录可包含：

```
.claude/
├── settings.local.json   # 本地权限设置
└── settings.json         # 共享的项目设置
```

**settings.local.json 示例**：

```json
{
  "permissions": {
    "allow": [
      "WebSearch",
      "WebFetch(domain:github.com)",
      "Bash(git status:*)",
      "Bash(npm test:*)"
    ]
  }
}
```

---

## 4. 组织方式与最佳实践

### 4.1 MCP 组织最佳实践

1. **按功能分组**：将相关的 MCP 服务器组织在一起
   ```json
   {
     "mcpServers": {
       "github": { ... },
       "database": { ... },
       "filesystem": { ... }
     }
   }
   ```

2. **环境变量管理**：敏感信息使用环境变量
   ```json
   {
     "mcpServers": {
       "github": {
         "env": {
           "GITHUB_TOKEN": "${GITHUB_TOKEN}"
         }
       }
     }
   }
   ```

3. **最小权限原则**：只授予必要的权限

### 4.2 Skills 组织最佳实践

1. **分类使用**：
   - 文档处理 → 使用 document-skills
   - 代码操作 → 使用内置代码技能
   - 外部服务 → 使用 MCP

2. **自定义技能命名**：使用清晰的命名约定
   ```
   /my-org-document    # 组织文档
   /my-api-docs        # API 文档
   ```

### 4.3 项目组织建议

```
project/
├── CLAUDE.md              # 项目指导文档
├── .claude/
│   └── settings.local.json  # 项目特定设置
├── docs/
│   └── ...                # 项目文档
└── src/
    └── ...                # 源代码
```

### 4.4 资源目录组织（针对本学习项目）

```
resources/
├── claude-code-mcp-skills-guide.md   # 本文档
├── github-mcp-server.md              # GitHub MCP 详细指南
├── mcp-servers/                      # MCP 服务器配置示例
│   ├── postgres.md
│   ├── slack.md
│   └── filesystem.md
└── skills-reference/                 # Skills 参考资料
    ├── document-skills.md
    └── custom-skills.md
```

---

## 5. 快速参考

### 5.1 常用命令速查

```bash
# 查看 MCP 状态
/mcp

# 查看帮助
/help

# 清除上下文
/clear
```

### 5.2 配置检查清单

- [ ] MCP 服务器配置正确
- [ ] API token 已设置且有效
- [ ] 权限配置合理
- [ ] 项目 CLAUDE.md 已创建
- [ ] 敏感信息未硬编码

### 5.3 故障排除

| 问题 | 可能原因 | 解决方案 |
|------|----------|----------|
| MCP 未连接 | 配置错误 | 检查 config.json 格式 |
| 权限拒绝 | 权限不足 | 在 settings.local.json 中添加权限 |
| Skill 不可用 | 技能未定义 | 确认技能名称或使用内置技能 |

---

## 6. 参考资源

- [MCP 官方文档](https://modelcontextprotocol.io/)
- [Claude Code 官方文档](https://claude.ai/code/docs)
- [MCP Servers GitHub](https://github.com/modelcontextprotocol/servers)
- [Smithery - MCP 服务器目录](https://smithery.ai/)

---

*最后更新：2026-02-27*
