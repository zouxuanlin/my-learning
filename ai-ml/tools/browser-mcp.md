# Browser MCP 完整指南

> 最后更新：2026-02-28

## 一、项目概述

**Browser MCP** 是一个 MCP（Model Context Protocol）服务器 + Chrome 扩展程序，允许你使用 AI 应用程序（如 VS Code、Claude、Cursor、Windsurf）来自动化浏览器操作。

### 项目信息

| 属性 | 值 |
|------|-----|
| **仓库** | [browsermcp/mcp](https://github.com/browsermcp/mcp) |
| **当前版本** | v0.1.3 |
| **作者** | Browser MCP / Namu |
| **许可证** | MIT |
| **官网** | [browsermcp.io](https://browsermcp.io) |
| **文档** | [docs.browsermcp.io](https://docs.browsermcp.io) |

---

## 二、核心特性

### 1. ⚡ 快速
- 自动化在本地机器上运行
- 无网络延迟，性能更好

### 2. 🔒 隐私
- 浏览器活动保留在本地设备
- 不会发送到远程服务器

### 3. 👤 已登录状态
- 使用现有的浏览器配置文件
- 保持所有服务的登录状态

### 4. 🥷🏼 隐蔽性
- 避免基本的机器人检测和 CAPTCHA
- 使用真实的浏览器指纹

---

## 三、架构设计

### 系统架构

```
┌─────────────────┐         WebSocket         ┌─────────────────┐
│   MCP Server    │ ◄───────────────────────► │  Chrome Extension │
│  (Node.js/TS)   │                           │   (Browser MCP)   │
└────────┬────────┘                           └─────────────────┘
         │
         │ Stdio
         ▼
┌─────────────────┐
│  AI Client      │
│ (Claude/Cursor) │
└─────────────────┘
```

### 核心组件

#### 1. MCP Server (`src/`)
- **index.ts** - 入口点，工具注册
- **server.ts** - MCP 服务器创建和请求处理
- **context.ts** - WebSocket 连接上下文管理
- **tools/** - 工具实现
- **resources/** - 资源处理
- **utils/** - 工具函数

#### 2. 通信机制
- **MCP Client ↔ Server**: Stdio 传输
- **Server ↔ Extension**: WebSocket 通信

---

## 四、可用工具（Tools）

Browser MCP 提供以下 11 个工具：

### 导航类工具

| 工具名 | 描述 | 参数 |
|--------|------|------|
| `navigate` | 导航到指定 URL | `url: string` |
| `go_back` | 浏览器后退 | 无 |
| `go_forward` | 浏览器前进 | 无 |

### 交互类工具

| 工具名 | 描述 | 参数 |
|--------|------|------|
| `click` | 点击页面元素 | `element: string` |
| `hover` | 悬停在元素上 | `element: string` |
| `type` | 向元素输入文本 | `element: string, text: string` |
| `select_option` | 选择下拉选项 | `element: string, options: string[]` |
| `press_key` | 按下键盘按键 | `key: string` |

### 信息类工具

| 工具名 | 描述 | 返回值 |
|--------|------|--------|
| `snapshot` | 获取页面 Aria 快照 | 页面结构和内容 |
| `get_console_logs` | 获取浏览器控制台日志 | 日志数组 |
| `screenshot` | 截取屏幕截图 | PNG 图像 |

### 其他工具

| 工具名 | 描述 | 参数 |
|--------|------|------|
| `wait` | 等待指定时间 | `time: number` (秒) |

---

## 五、安装与配置

### 前置要求

- Node.js 18+
- npm 或 pnpm
- Chrome 浏览器

### 步骤 1：安装 Chrome 扩展

1. 访问 [Chrome Web Store](https://chrome.google.com/webstore) 搜索 "Browser MCP"
2. 或从 GitHub 下载源码手动安装

### 步骤 2：安装 MCP Server

```bash
# 使用 npm 全局安装
npm install -g @browsermcp/mcp

# 或使用 npx 直接运行
npx @browsermcp/mcp
```

### 步骤 3：配置 MCP Client

#### Claude Desktop 配置

编辑 `claude_desktop_config.json`：

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

#### Cursor 配置

编辑 `.cursor/mcp.json`：

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

### 步骤 4：连接浏览器

1. 点击浏览器工具栏中的 Browser MCP 扩展图标
2. 点击 "Connect" 按钮连接当前标签页
3. 在 AI 客户端中开始使用

---

## 六、使用示例

### 示例 1：导航并获取页面内容

```
请打开 https://example.com 并告诉我页面的主要内容
```

### 示例 2：截图

```
截取当前页面的截图
```

### 示例 3：表单填写

```
在登录页面输入用户名 "test" 和密码 "123456"，然后点击登录按钮
```

### 示例 4：获取控制台日志

```
查看页面的控制台是否有错误日志
```

### 示例 5：复杂操作

```
1. 打开 https://github.com
2. 搜索 "browsermcp"
3. 进入第一个仓库
4. 获取页面摘要
```

---

## 七、技术细节

### 工具实现流程

```
AI 请求 → MCP Server → WebSocket → Chrome Extension → 浏览器操作
                                        ↓
                                    返回结果
```

### 核心代码结构

#### 工具定义 (`src/tools/tool.ts`)

```typescript
export type Tool = {
  schema: ToolSchema;
  handle: (context: Context, params?: any) => Promise<CallToolResult>;
};
```

#### 上下文管理 (`src/context.ts`)

```typescript
export class Context {
  ws: WebSocket;
  sendSocketMessage<T>(type: T, payload: any, options?: any): Promise<any>;
  close(): Promise<void>;
}
```

### 依赖项

| 依赖 | 用途 |
|------|------|
| `@modelcontextprotocol/sdk` | MCP 协议实现 |
| `commander` | 命令行参数解析 |
| `ws` | WebSocket 通信 |
| `zod` | 参数验证 |
| `zod-to-json-schema` | JSON Schema 生成 |

---

## 八、与 Playwright MCP 对比

| 特性 | Browser MCP | Playwright MCP |
|------|-------------|----------------|
| **浏览器实例** | 使用用户现有浏览器 | 创建新浏览器实例 |
| **登录状态** | ✅ 保持登录 | ❌ 需重新登录 |
| **机器人检测** | ✅ 较难检测 | ⚠️ 易被检测 |
| **隐私** | ✅ 本地运行 | ✅ 本地运行 |
| **配置复杂度** | 中等 | 较低 |

---

## 九、限制与注意事项

### 当前限制

1. **依赖关系**：核心代码依赖于 monorepo 中的 utils 和 types，目前无法独立构建
2. **仅支持 Chrome**：暂不支持 Firefox、Safari 等其他浏览器
3. **手动连接**：需要手动点击扩展程序连接标签页

### 安全注意事项

- ⚠️ 仅连接可信的标签页
- ⚠️ 避免在敏感页面（银行、密码管理器）使用
- ⚠️ 注意 AI 可能执行意外操作

---

## 十、故障排除

### 问题 1："No connection to browser extension"

**原因**：Chrome 扩展未连接
**解决**：点击扩展图标 → 点击 "Connect"

### 问题 2：工具执行超时

**原因**：页面加载慢或操作复杂
**解决**：增加 `wait` 工具调用或使用更长超时时间

### 问题 3：元素找不到

**原因**：页面未完全加载或元素选择器错误
**解决**：先调用 `snapshot` 确认页面状态

---

## 十一、开发指南

### 本地开发

```bash
# 克隆仓库
git clone https://github.com/browsermcp/mcp.git

# 安装依赖
npm install

# 构建
npm run build

# 监听模式
npm run watch

# 使用 inspector 调试
npm run inspector
```

### 添加自定义工具

1. 在 `src/tools/` 创建新工具文件
2. 定义工具 Schema 和 handle 函数
3. 在 `src/index.ts` 注册工具

---

## 十二、相关资源

### 官方资源
- [官方网站](https://browsermcp.io)
- [官方文档](https://docs.browsermcp.io)
- [GitHub 仓库](https://github.com/browsermcp/mcp)

### 相关项目
- [Playwright MCP](https://github.com/microsoft/playwright-mcp) - Browser MCP 的灵感来源
- [Model Context Protocol](https://modelcontextprotocol.io) - MCP 协议规范

---

## 总结

Browser MCP 是一个强大的浏览器自动化工具，通过 MCP 协议将 AI 与浏览器无缝连接。其主要优势在于：

✅ **本地运行** - 隐私和安全
✅ **保持登录** - 使用现有会话
✅ **易于使用** - 简单的 MCP 配置
✅ **AI 友好** - 专为 AI 自动化设计

最适合需要**自动化 Web 操作**、**数据收集**、**UI 测试**等场景。
