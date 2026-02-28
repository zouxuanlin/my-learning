# Browser MCP 完整指南

> 最后更新：2026-02-28

## 概述

**Browser MCP** 是一个 MCP（Model Context Protocol）服务器 + Chrome 扩展程序，允许你使用 AI 应用（如 VS Code、Claude、Cursor 和 Windsurf）来自动化浏览器操作。

官方网站：https://browsermcp.io
官方文档：https://docs.browsermcp.io
GitHub 项目：https://github.com/BrowserMCP/mcp

## 主要特性

- ⚡ **快速**：自动化在本地机器上运行，无需网络延迟
- 🔒 **隐私**：浏览器活动保留在本地设备，不会发送到远程服务器
- 👤 **已登录状态**：使用现有浏览器配置文件，保持所有服务的登录状态
- 🥷🏼 **隐蔽**：使用真实的浏览器指纹，避免基础机器人检测和 CAPTCHA

## 安装指南

### 第一步：前置要求

需要安装 **Node.js** 才能使用 Browser MCP 服务器。

下载地址：https://nodejs.org/en/download

### 第二步：配置 MCP 服务器

将以下 MCP 服务器配置添加到支持 MCP 的 AI 应用中：

**支持的 AI 应用：**
- Cursor
- Claude Desktop
- Windsurf
- VS Code

**MCP 服务器配置：**

```json
{
  "mcpServers": {
    "browsermcp": {
      "command": "npx",
      "args": ["@browsermcp/mcp@latest"]
    }
  }
}
```

> **注意**：如果遇到 "Client closed" 错误，尝试移除配置中的 `@latest`，使用 `@browsermcp/mcp` 代替 `@browsermcp/mcp@latest`

### 第三步：安装浏览器扩展

1. 安装 **Browser MCP 扩展程序**
   - Chrome Web Store 地址：https://chromewebstore.google.com/detail/browser-mcp-automate-your/bjfgambnhccakkhmkepdoekmckoijdlc

2. 固定 Browser MCP 扩展程序到工具栏以便快速访问

3. 点击扩展程序图标打开 Browser MCP 扩展

4. 点击 **"Connect"** 按钮，将当前标签页连接到 MCP 服务器
   - 所有浏览器操作将在已连接的标签页上执行

## 开始使用

配置完成后，可以在 MCP 客户端（如 Cursor、Claude Code）中运行命令来测试。

**测试命令示例：**

```
Go to google.com and search for "Browser MCP"
```

## 故障排除

### 常见问题

#### 1. MCP 服务器未运行

如果 MCP 服务器未运行，执行使用 MCP 服务器的命令时会出错。

**解决方法：**
- 在 AI 应用中查看 MCP 服务器列表
- 确保 Browser MCP 服务器处于运行状态
- 检查服务器连接状态（Disconnected → Connected）

#### 2. Client closed 错误

如果看到 "Client closed" 消息，且点击 reload 无法解决：

**解决方法：**
- 从 MCP 服务器配置中移除 `@latest`
- 使用 `@browsermcp/mcp` 代替 `@browsermcp/mcp@latest`

#### 3. 浏览器未连接到 MCP 服务器

**解决方法：**
- 安装 Browser MCP 扩展程序
- 点击扩展程序中的 "Connect" 按钮

#### 4. 其他错误

如果遇到其他错误，请在 GitHub 上提交 issue：
https://github.com/BrowserMCP/mcp/issues

## 工作流程示意

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│  AI 应用     │────▶│  MCP Server  │────▶│  浏览器     │
│ (Cursor/    │     │  (npx)       │     │  (扩展程序)  │
│  Claude)    │◀────│              │◀────│             │
└─────────────┘     └──────────────┘     └─────────────┘
```

## 项目来源

Browser MCP 是从 [Playwright MCP server](https://github.com/microsoft/playwright-mcp) 改编而来，使用用户的真实浏览器进行自动化操作，而非创建新的浏览器实例。这样可以：
- 使用现有的浏览器配置文件
- 保持登录状态
- 避免常见的机器人检测机制

## 相关资源

- 官方安装页面：https://browsermcp.io/install
- 视频教程（YouTube）：
  - "Browser MCP with Cursor: Automate Tasks and Testing"
  - "Automate your browser with Browser MCP"
- Reddit 讨论：r/ClaudeAI 上的用户讨论
