# Notion MCP Server 配置指南

## 快速开始

### 1. 获取 Notion Integration Token

1. 访问 [https://www.notion.so/profile/integrations](https://www.notion.so/profile/integrations)
2. 点击 "+ New integration" 或选择一个已有的 integration
3. 在 "Configuration" 标签页复制你的 Internal Integration Token（以 `ntn_` 开头）

![获取 Token](https://github.com/user-attachments/assets/67b44536-5333-49fa-809c-59581bf5370a)

### 2. 授予页面访问权限

**方法一：通过 Integration 设置**
1. 在 integration 页面点击 "Access" 标签
2. 点击 "Edit access"
3. 选择你想要访问的页面

**方法二：通过页面设置**
1. 打开想要连接的 Notion 页面
2. 点击右上角 "···" → "Connect to"
3. 选择你的 integration

### 3. 配置 Token

编辑 `.claude/mcp.json` 文件，将 `ntn_YOUR_TOKEN_HERE` 替换为你的实际 token：

```json
{
  "mcpServers": {
    "notion": {
      "command": "npx",
      "args": ["-y", "@notionhq/notion-mcp-server"],
      "env": {
        "NOTION_TOKEN": "ntn_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
      }
    }
  }
}
```

### 4. 验证配置

在 Claude Code 中输入以下命令验证配置是否生效：

```
/mcp list
```

如果看到 `notion` 服务器在列表中，说明配置成功！

---

## 可用工具

Notion MCP Server 提供以下 22 个工具：

### 内容操作
| 工具名 | 描述 |
|--------|------|
| `search` | 搜索页面和数据源 |
| `get-a-page` | 获取页面内容 |
| `create-a-page` | 创建新页面 |
| `update-a-page` | 更新页面内容 |
| `delete-a-page` | 删除页面 |
| `move-page` | 移动页面位置 |

### 数据源（数据库）操作
| 工具名 | 描述 |
|--------|------|
| `query-data-source` | 查询数据源（数据库） |
| `retrieve-a-data-source` | 获取数据源元数据 |
| `update-a-data-source` | 更新数据源属性 |
| `create-a-data-source` | 创建新数据源 |
| `list-data-source-templates` | 列出模板 |
| `retrieve-a-database` | 获取数据库元数据 |

### 互动
| 工具名 | 描述 |
|--------|------|
| `add-comment-to-page` | 在页面添加评论 |

---

## 使用示例

### 搜索页面
```
搜索我的 Notion 中关于"学习笔记"的页面
```

### 创建页面
```
在"个人知识库"下创建一个新页面，标题为"2026 年学习计划"
```

### 查询数据库
```
查看我的任务数据库，显示所有未完成任务
```

### 添加评论
```
在"项目文档"页面添加评论"已更新，请查阅"
```

---

## 故障排除

### 问题：Token 无效
- 确认 token 以 `ntn_` 开头
- 确认 token 没有复制错或包含空格

### 问题：无法访问页面
- 确认已在 Notion 中授予 integration 访问权限
- 检查页面是否在已连接的 workspace 中

### 问题：npx 命令不存在
- 确保已安装 Node.js 和 npm
- 运行 `npm install -g npx` 安装

---

## 相关链接

- [官方文档](https://developers.notion.com/docs/mcp)
- [GitHub 仓库](https://github.com/makenotion/notion-mcp-server)
- [Notion API 参考](https://developers.notion.com/reference/intro)
