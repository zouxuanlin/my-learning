# OpenClaw Agent 提示词技巧整理

> 整理时间：2025-04-08

本文档系统整理了 OpenClaw Agent 的提示词工程最佳实践和使用技巧，帮助用户更高效地与 AI 代理交互。

## 目录

1. [核心原则](#1-核心原则)
2. [技能（Skills）系统使用](#2-技能skills系统使用)
3. [工具调用优化](#3-工具调用优化)
4. [上下文管理](#4-上下文管理)
5. [安全与权限](#5-安全与权限)
6. [调试与故障排除](#6-调试与故障排除)

## 1. 核心原则

### 1.1 明确指令优先

OpenClaw Agent 遵循明确的指令优于模糊请求：

✅ **推荐**：
```
帮我提交 my-learning 仓库的所有更改到 GitHub
```

❌ **不推荐**：
```
能帮我做点什么吗？
```

### 1.2 具体任务分解

将复杂任务分解为具体步骤：

✅ **推荐**：
```
1. 检查 my-learning 目录是否有未提交的更改
2. 如果有，添加所有文件并提交
3. 推送到 GitHub 远程仓库
```

### 1.3 上下文提供

提供必要的上下文信息，避免让 Agent 猜测：

✅ **推荐**：
```
在 my-learning 仓库中，帮我整理 OpenClaw Agent 的提示词技巧文档
```

❌ **不推荐**：
```
帮我整理提示词技巧文档
```

## 2. 技能（Skills）系统使用

### 2.1 技能识别与调用

OpenClaw 通过技能系统扩展功能。用户可以通过以下方式触发技能：

#### 斜杠命令语法
```
/skill-name [参数]
```

常用内置技能：
- `/help` - 显示帮助信息
- `/clear` - 清除对话上下文
- 自定义技能（如天气查询、GitHub 操作等）

#### 自然语言触发
Agent 能够根据任务描述自动选择合适的技能：

```
帮我查询北京的天气 → 自动调用 weather 技能
帮我创建 git 提交 → 自动调用 git 相关功能
```

### 2.2 技能开发最佳实践

当创建自定义技能时，遵循以下规范：

#### SKILL.md 结构
```markdown
---
name: skill-name
description: 技能简短描述
metadata:
  {
    "openclaw": {
      "emoji": "🔧",
      "requires": { "bins": ["required-bin"], "env": ["REQUIRED_ENV"] }
    }
  }
---

# 技能名称

## 功能描述
详细说明技能功能

## 使用方法
### 命令格式
```
/skill-name [参数]
```

## 示例
具体使用示例

## 注意事项
安全提示和限制
```

#### 命名规范
- 使用小写字母和连字符
- 名称应简洁描述功能
- 避免与现有技能冲突

## 3. 工具调用优化

### 3.1 文件操作

#### 读取文件
```
读取 MEMORY.md 文件的内容
```

#### 写入文件
```
将以下内容保存到 memory/2025-04-08.md
```

#### 编辑文件
```
在 MEMORY.md 中添加关于 my-learning 仓库的说明
```

### 3.2 执行命令

#### Shell 命令
```
在 my-learning 目录下执行 git status
```

#### Git 操作
```
提交 my-learning 仓库的更改到 GitHub
```

### 3.3 网络操作

#### 网页搜索
优先使用本地 SearXNG 实例进行隐私保护搜索：

```
使用 searxng 搜索 OpenClaw 文档
```

#### 网页抓取
```
抓取 https://docs.openclaw.ai 的主要内容
```

## 4. 上下文管理

### 4.1 记忆系统

OpenClaw 使用分层记忆系统：

#### 长期记忆（MEMORY.md）
- 存储重要决策、偏好和长期上下文
- 仅在主会话中加载
- 用户可自由编辑

#### 日常记忆（memory/YYYY-MM-DD.md）
- 存储每日活动和临时上下文
- 自动按日期组织
- 用于短期连续性

### 4.2 工作空间组织

合理组织工作空间提高效率：

```
workspace/
├── AGENTS.md          # 代理配置
├── SOUL.md            # 代理人格定义
├── USER.md            # 用户信息
├── MEMORY.md          # 长期记忆
├── memory/            # 日常记忆目录
├── skills/            # 自定义技能
└── my-learning/       # 用户学习仓库
```

### 4.3 会话管理

#### 心跳机制
定期检查重要事项：
- 邮件和通知
- 日历事件
- 天气更新
- 项目状态

#### 子代理会话
对于复杂或长时间任务，使用子代理：

```
spawn a sub-agent to research OpenClaw documentation
```

## 5. 安全与权限

### 5.1 权限原则

- **最小权限**：只授予必要权限
- **敏感信息保护**：不在日志中暴露密钥
- **外部操作确认**：对破坏性操作要求确认

### 5.2 安全配置

#### 密钥管理
使用 SecretRef 方式管理敏感信息：

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

#### 环境隔离
- 工作空间文件可自由操作
- 外部操作（邮件、社交媒体）需确认
- 破坏性命令（删除文件）需谨慎

## 6. 调试与故障排除

### 6.1 常见问题

#### 技能未加载
- 检查 SKILL.md 格式是否正确
- 确认技能目录位置
- 查看日志：`openclaw gateway logs | grep -i skill`

#### 工具调用失败
- 检查二进制文件是否存在：`which tool-name`
- 验证环境变量：`echo $ENV_VAR`
- 确认权限配置

### 6.2 调试技巧

#### 启用调试日志
```json
{
  "logging": {
    "level": "debug",
    "skills": true
  }
}
```

#### 会话状态检查
使用 `/status` 命令查看当前状态：

```
📊 session_status
```

#### 工具可用性验证
在执行前验证工具是否可用：

```
先检查 my-learning 目录是否存在未提交的更改
```

## 参考资源

- [OpenClaw 官方文档](https://docs.openclaw.ai)
- [ClawHub 技能市场](https://clawhub.com)
- [AgentSkills 规范](https://agentskills.io)
- 本地技能文档：`/opt/openclaw/skills/`