# OpenClaw 使用案例汇总

> 文档更新时间：2026-03-01
> 来源：https://docs.openclaw.ai

## 什么是 OpenClaw？

OpenClaw 是一个自托管的 AI 代理网关，将你喜欢的聊天应用（WhatsApp、Telegram、Discord、iMessage 等）连接到 AI 编码代理。

### 核心特点

- **自托管**：运行在你的硬件上，你的规则
- **多通道**：一个网关同时服务 WhatsApp、Telegram、Discord 等
- **代理原生**：为编码代理构建，支持工具使用、会话、记忆和多代理路由
- **开源**：MIT 许可，社区驱动

---

## 使用案例分类

### 1. 个人 AI 助手

#### 场景描述
通过任意聊天应用随时访问个人 AI 助手，无需依赖托管服务。

#### 典型配置
- **通道**：WhatsApp 或 Telegram（最常用）
- **模型**：Anthropic Claude、OpenAI GPT 等
- **技能**：文件操作、网页搜索、浏览器自动化

#### 优势
- 数据隐私：所有数据在本地处理
- 随时随地：从手机、电脑任意设备访问
- 高度可定制：根据需求配置技能和工具

---

### 2. 开发工作流自动化

#### 场景描述
将 OpenClaw 集成到日常开发工作中，自动化常见任务。

#### 典型用例

| 用例 | 工具 | 说明 |
|------|------|------|
| 代码审查 | `read`, `exec` | 读取代码文件，运行测试 |
| Git 操作 | `exec` | 提交、推送、分支管理 |
| 文档生成 | `read`, `write` | 自动生成和更新文档 |
| 问题排查 | `exec`, `read` | 查看日志，诊断问题 |
| 部署脚本 | `exec` | 运行部署命令 |

#### 配置示例
```json
{
  "tools": {
    "profile": "coding",
    "allow": ["group:fs", "group:runtime", "group:sessions"]
  }
}
```

---

### 3. 团队协作机器人

#### 场景描述
在团队聊天工具中部署 AI 助手，协助团队工作。

#### 支持平台
- **Discord**：服务器、频道、DM 支持
- **Slack**：工作区应用
- **Telegram**：群组支持
- **Microsoft Teams**：企业支持（插件）

#### 典型功能
- 回答技术问题
- 代码片段分享
- 任务跟踪和提醒
- 会议纪要生成

#### 安全配置
```json
{
  "channels": {
    "discord": {
      "allowFrom": ["user-id-1", "user-id-2"],
      "groups": {
        "*": { "requireMention": true }
      }
    }
  }
}
```

---

### 4. 智能家居控制

#### 场景描述
通过聊天应用控制智能家居设备。

#### 实现方式
- 使用 `exec` 工具调用智能家居 CLI
- 集成 Home Assistant API
- 定时任务（cron）自动化

#### 示例命令
```
"打开客厅灯"
"设置空调到 25 度"
"查看摄像头状态"
```

---

### 5. 信息聚合与监控

#### 场景描述
聚合多个信息源，定时推送摘要。

#### 可用工具
- `web_search`：搜索网络信息
- `web_fetch`：抓取网页内容
- `cron`：定时任务
- `message`：发送通知

#### 典型应用
- 新闻摘要（每日/每周）
- 股票价格监控
- 天气预警
- RSS 订阅聚合

#### 定时任务示例
```json
{
  "name": "daily-news",
  "schedule": { "kind": "cron", "expr": "0 8 * * *" },
  "payload": { "kind": "agentTurn", "message": "生成今日新闻摘要" }
}
```

---

### 6. 学习与知识管理

#### 场景描述
构建个人知识库，辅助学习。

#### 功能
- 笔记整理和搜索（`memory_search`, `memory_get`）
- 网页内容保存（`web_fetch`）
- 文档生成（`write`）
- 问题解答

#### 技能示例
- 语言学习助手
- 编程教程生成
- 概念解释
- 参考资料整理

---

### 7. 多代理系统

#### 场景描述
运行多个专用代理，每个代理负责特定任务。

#### 代理类型
| 代理 | 用途 | 工具限制 |
|------|------|----------|
| `main` | 通用助手 | 全部工具 |
| `support` | 客服支持 | 仅消息工具 |
| `coder` | 编程助手 | 文件系统 + 运行时 |
| `researcher` | 研究助手 | 网页搜索 + 浏览器 |

#### 配置示例
```json
{
  "agents": {
    "list": [
      {
        "id": "support",
        "tools": { "profile": "messaging", "allow": ["slack"] }
      },
      {
        "id": "coder",
        "tools": { "profile": "coding" }
      }
    ]
  }
}
```

---

### 8. 浏览器自动化

#### 场景描述
自动化网页操作和数据处理。

#### 可用操作
- 页面导航
- 元素点击/输入
- 截图
- PDF 生成
- 数据提取

#### 典型应用
- 网页数据抓取
- 自动化测试
- 表单填写
- 报告生成

---

### 9. 远程服务器管理

#### 场景描述
通过聊天应用管理远程服务器。

#### 功能
- SSH 命令执行
- 服务状态监控
- 日志查看
- 备份管理

#### 节点支持
- macOS 节点（完整功能）
- Linux 节点（通过 `nodes` 工具）
- 摄像头/屏幕录制（需要节点应用）

---

### 10. 媒体处理

#### 场景描述
处理和生成多媒体内容。

#### 可用工具
- `image`：图像分析
- `tts`：文本转语音
- `browser.screenshot`：网页截图
- `canvas.snapshot`：画布截图

#### 应用场景
- 图片内容识别
- 语音消息生成
- 可视化报告
- 缩略图生成

---

## 支持的通信渠道

### 核心渠道
| 渠道 | 类型 | 特点 |
|------|------|------|
| WhatsApp | 个人/群组 | 最流行，需 QR 配对 |
| Telegram | 机器人 API | 简单，支持群组 |
| Discord | 机器人 API | 服务器/频道/DM |
| IRC | 经典协议 | 频道 + DM |
| Slack | Bolt SDK | 工作区应用 |
| Signal | signal-cli | 隐私优先 |
| BlueBubbles | REST API | iMessage 推荐方案 |
| WebChat | WebSocket | 网关内置 UI |

### 插件渠道
- Feishu/Lark（飞书）
- Mattermost
- Google Chat
- Microsoft Teams
- LINE
- Matrix
- Nextcloud Talk
- Synology Chat
- 以及更多...

---

## 技能（Skills）生态系统

### 内置技能
- `weather`：天气查询
- `healthcheck`：系统安全检查
- `searxng`：隐私搜索
- `qqbot-cron`：QQ 机器人定时任务
- `qqbot-media`：QQ 媒体发送

### ClawHub 技能市场
访问 https://clawhub.com 发现和安装社区技能：
- 安装：`clawhub install <skill-name>`
- 更新：`clawhub update --all`
- 同步：`clawhub sync --all`

---

## MCP（Model Context Protocol）集成

OpenClaw 支持 MCP 协议，可以连接各种 MCP 服务器：

### 官方 MCP 服务器
- **Filesystem**：文件系统访问
- **Git**：Git 仓库操作
- **Memory**：知识图谱记忆
- **Fetch**：网页内容获取
- **Time**：时间/时区转换
- **Sequential Thinking**：序列思考

### 安装示例
```bash
# 安装文件系统 MCP 服务器
npm install -g @modelcontextprotocol/server-filesystem

# 运行
npx -y @modelcontextprotocol/server-filesystem /path/to/allowed/dir
```

---

## 安全最佳实践

### 1. 访问控制
```json
{
  "channels": {
    "whatsapp": {
      "allowFrom": ["+15555550123"]
    }
  },
  "messages": {
    "groupChat": {
      "mentionPatterns": ["@openclaw"]
    }
  }
}
```

### 2. 工具限制
```json
{
  "tools": {
    "deny": ["browser", "exec"],
    "profile": "messaging"
  }
}
```

### 3. 沙箱执行
```json
{
  "agents": {
    "defaults": {
      "sandbox": {
        "enabled": true,
        "docker": {
          "image": "node:22-alpine"
        }
      }
    }
  }
}
```

### 4. 敏感信息保护
- 使用 SecretRef 存储 API 密钥
- 不在提示词中包含敏感信息
- 定期审查技能代码

---

## 性能优化

### 1. 会话管理
- 使用 `sessions_list` 监控活跃会话
- 设置合理的 `activeMinutes` 过滤
- 定期清理旧会话

### 2. 技能加载
```json
{
  "skills": {
    "load": {
      "watch": true,
      "watchDebounceMs": 250
    }
  }
}
```

### 3. 缓存配置
- Web 搜索结果缓存（默认 15 分钟）
- 浏览器配置文件复用
- 会话状态快照

---

## 故障排除

### 常见问题

| 问题 | 可能原因 | 解决方案 |
|------|----------|----------|
| 通道连接失败 | 配置错误/网络问题 | 检查配置，查看日志 |
| 技能不加载 | 依赖缺失 | 安装所需二进制/环境变量 |
| 工具调用失败 | 权限不足 | 检查工具允许列表 |
| 内存占用高 | 会话过多 | 清理旧会话，限制 history |
| 浏览器启动失败 | 端口冲突 | 更改配置文件端口 |

### 日志位置
- 默认：`~/.openclaw/logs/`
- 实时查看：`openclaw gateway logs`

---

## 参考资源

- **官方文档**：https://docs.openclaw.ai
- **GitHub**：https://github.com/openclaw/openclaw
- **技能市场**：https://clawhub.com
- **社区**：https://discord.com/invite/clawd

---

## 更新日志

- 2026-03-01：初始版本，汇总官方文档用例
