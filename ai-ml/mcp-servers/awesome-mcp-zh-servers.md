# Awesome-MCP-ZH MCP 服务器分类整理

> 来源：[Awesome-MCP-ZH](https://github.com/yzfly/Awesome-MCP-ZH)  
> 整理时间：2026-02-28  

本文档整理了 Awesome-MCP-ZH 项目中所有的 MCP 服务器，按功能分类。

---

## 目录

- [🌐 浏览器自动化与网页交互](#🌐-浏览器自动化与网页交互)
- [💻 开发与代码执行](#💻-开发与代码执行)
- [🖥️ 命令行与 Shell 交互](#🖥️-命令行与-Shell-交互)
- [🔄 版本控制 (Git / GitHub / GitLab)](#🔄-版本控制-Git---GitHub---GitLab)
- [🗄️ 数据库交互](#🗄️-数据库交互)
- [☁️ 云平台与服务集成 (AWS, Cloudflare, Azure, K8s, etc.)](#☁️-云平台与服务集成-AWS,-Cloudflare,-Azure,-K8s,-etc.)
- [🔍 搜索](#🔍-搜索)
- [💬 通讯与协作 (Slack, Email, Calendar, Social, etc.)](#💬-通讯与协作-Slack,-Email,-Calendar,-Social,-etc.)
- [💰 金融与加密货币](#💰-金融与加密货币)
- [📁 文件系统与存储](#📁-文件系统与存储)
- [📊 数据分析、处理与可视化](#📊-数据分析、处理与可视化)
- [🛠️ 效率工具与集成 (Office, Project Management, Notes, etc.)](#🛠️-效率工具与集成-Office,-Project-Management,-Notes,-etc.)
- [multimedia 多媒体与内容创作](#multimedia-多媒体与内容创作)
- [📕 社交媒体与内容创作 (小红书/RedNote)](#📕-社交媒体与内容创作-小红书-RedNote)
- [🧠 知识、记忆与 RAG](#🧠-知识、记忆与-RAG)
- [🔒 安全与分析](#🔒-安全与分析)
- [🌍 地理位置与出行](#🌍-地理位置与出行)
- [🏃 体育与游戏](#🏃-体育与游戏)
- [🏛️ 艺术与文化](#🏛️-艺术与文化)
- [🛠️ 其他实用工具与集成](#🛠️-其他实用工具与集成)

---

## 🌐 浏览器自动化与网页交互

让 AI 能够像人一样浏览网页、提取信息、填写表单等

### 1. [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp)

- **描述**: 微软官方出品，使用 Playwright 让 AI 精确控制网页，自动化抓取数据。

- **备注**: 官方实现，浏览器自动化强推，适合需要精细网页交互的场景。

### 2. [browserbase/mcp-server-browserbase](https://github.com/browserbase/mcp-server-browserbase)

- **描述**: 云端浏览器自动化服务，能导航网页、提取数据、填表单等，无需本地安装。

- **备注**: 官方实现 (Browserbase) 🎖️, TypeScript 开发 📇, 云端浏览器操作。

### 3. [modelcontextprotocol/server-puppeteer](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer)

- **描述**: 官方参考实现，使用 Puppeteer 进行浏览器自动化和网页抓取。

- **备注**: 官方参考, TypeScript 开发 📇, 本地运行 🏠, 网页抓取和交互基础工具。

### 4. [apify/actors-mcp-server](https://github.com/apify/actors-mcp-server)

- **描述**: 集成 Apify 平台 3000+ 云工具，用于网站、电商、社交媒体等数据提取。

- **备注**: 官方实现 (Apify), TypeScript 开发 📇, 云端数据抓取工具库 ☁️。

### 5. [AgentQL](https://github.com/tinyfish-io/agentql-mcp)

- **描述**: 让 AI 代理从非结构化网页中获取结构化数据。

- **备注**: 官方实现 (TinyFish IO) 🎖️, TypeScript 开发 📇, 网页数据结构化提取 ☁️。

### 6. [Firecrawl](https://github.com/mendableai/firecrawl-mcp-server)

- **描述**: 使用 Firecrawl 提取网页数据，支持 JavaScript 渲染。

- **备注**: 官方实现 (Mendable AI), TypeScript 开发, 高级网页抓取。

### 7. [Oxylabs](https://github.com/oxylabs/oxylabs-mcp)

- **描述**: 使用 Oxylabs Web API 抓取网站，支持动态渲染和结构化数据提取。

- **备注**: 官方实现 (Oxylabs), Python 开发, 专业级网页抓取。

### 8. [Hyperbrowser](https://github.com/hyperbrowserai/mcp)

- **描述**: 新一代 AI 代理浏览器自动化平台，支持大规模、无缝操作。

- **备注**: 官方实现 (Hyperbrowser AI), TypeScript 开发, 大规模浏览器自动化。

### 9. [ScreenshotOne](https://github.com/screenshotone/mcp/)

- **描述**: 使用 ScreenshotOne 服务渲染网站截图。

- **备注**: 官方实现 (ScreenshotOne), TypeScript 开发, 网页截图工具。

### 10. [modelcontextprotocol/server-fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch)

- **描述**: 官方参考实现，灵活获取网页内容（HTML/JSON/MD），并为 AI 处理优化。

- **备注**: 官方参考, Python 开发 🐍, 本地/云端 🏠☁️, 基础网页内容获取。

### 11. [automatalabs/mcp-server-playwright](https://github.com/Automata-Labs-team/MCP-Server-Playwright)

- **描述**: 使用 Playwright 进行浏览器自动化的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍.

### 12. [blackwhite084/playwright-plus-python-mcp](https://github.com/blackwhite084/playwright-plus-python-mcp)

- **描述**: 使用 Playwright 的 Python MCP 服务器，更适合 LLM。

- **备注**: 社区实现, Python 开发 🐍.

### 13. [browsermcp/mcp](https://github.com/browsermcp/mcp)

- **描述**: 自动化本地 Chrome 浏览器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠.

### 14. [co-browser/browser-use-mcp-server](https://github.com/co-browser/browser-use-mcp-server)

- **描述**: 将 browser-use 打包为带 SSE 传输的 MCP 服务器，含 Dockerfile。

- **备注**: 社区实现, Python 开发 🐍.

### 15. [executeautomation/playwright-mcp-server](https://github.com/executeautomation/mcp-playwright)

- **描述**: 使用 Playwright 进行浏览器自动化和网页抓取的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇.

### 16. [flutter-skill](https://github.com/ai-dashboad/flutter-skill)

- **描述**: AI驱动的E2E测试MCP服务器，支持Flutter、iOS、Android、Web、Electron、Tauri、KMP、React Native、.NET MAUI等8个平台。

- **备注**: 社区实现, Dart 开发, E2E跨平台测试。

### 17. [eyalzh/browser-control-mcp](https://github.com/eyalzh/browser-control-mcp)

- **描述**: 与浏览器扩展配对，使 LLM 客户端能控制用户的 Firefox 浏览器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠.

### 18. [getrupt/ashra-mcp](https://github.com/getrupt/ashra-mcp)

- **描述**: 从任何网站提取结构化数据，只需提示即可获得 JSON。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠.

### 19. [kimtth/mcp-aoai-web-browsing](https://github.com/kimtth/mcp-aoai-web-browsing)

- **描述**: 使用 Azure OpenAI 和 Playwright 的最小化 MCP 服务器/客户端实现。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠.

### 20. [ndthanhdev/mcp-browser-kit](https://github.com/ndthanhdev/mcp-browser-kit)

- **描述**: 用于与 manifest v2 兼容浏览器交互的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠.

### 21. [RAG Web Browser](https://github.com/apify/mcp-server-rag-web-browser)

- **描述**: Apify 开源工具，执行网页搜索、抓取 URL 并以 Markdown 格式返回内容。

- **备注**: 社区实现 (Apify), TypeScript 开发 📇, 结合 RAG 的网页浏览 ☁️。

### 22. [scrapling-fetch](https://github.com/cyberchitta/scrapling-fetch-mcp)

- **描述**: 从有反爬虫措施的网站获取文本内容。

- **备注**: 社区实现, Python 开发, 突破反爬。

### 23. [jae-jae/fetcher-mcp](https://github.com/jae-jae/fetcher-mcp)

- **描述**: 使用 Playwright 无头浏览器获取网页内容，支持 JS 渲染和智能提取 (Markdown/HTML)。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Playwright 网页内容提取。

### 24. [ryoppippi/sitemcp](https://github.com/ryoppippi/sitemcp)

- **描述**: 抓取整个网站并将其作为 MCP 服务器使用。

- **备注**: 支持 TypeScript，提供工具命名策略、页面匹配、内容选择器等功能。可通过 NPM、Bun 等安装和运行。

### 25. [34892002/bilibili-mcp-js](https://github.com/34892002/bilibili-mcp-js)

- **描述**: 支持搜索 Bilibili 内容的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠.

---

## 💻 开发与代码执行

让 AI 能够运行代码、分析代码库、与开发工具集成等

### 1. [21st.dev Magic](https://github.com/21st-dev/magic-mcp)

- **描述**: 21st.dev 官方集成，创建受顶级设计工程师启发的精美 UI 组件。

- **备注**: 官方实现 (21st.dev) 🎖️, UI 组件创建。

### 2. [pydantic/pydantic-ai/mcp-run-python](https://github.com/pydantic/pydantic-ai/tree/main/mcp-run-python)

- **描述**: Pydantic 出品，在安全的沙盒环境中运行 Python 代码，适合开发编程代理。

- **备注**: 官方实现 (Pydantic) 🎖️, Python 开发 🐍, 本地运行 🏠, 安全代码执行。

### 3. [E2B](https://github.com/e2b-dev/mcp-server)

- **描述**: 在 E2B 提供的安全云沙盒中运行代码。

- **备注**: 官方实现 (E2B), TypeScript 开发, 云端安全代码沙盒。

### 4. [JetBrains IDE Proxy](https://github.com/JetBrains/mcpProxy)

- **描述**: JetBrains 官方代理，连接到 JetBrains IDE。

- **备注**: 官方实现 (JetBrains) 🎖️, TypeScript 开发 📇, 本地运行 🏠, IDE 连接。

### 5. [JetBrains](https://github.com/JetBrains/mcp-jetbrains)

- **描述**: JetBrains 官方集成，让 AI 在 JetBrains IDE 中处理代码。

- **备注**: 官方实现 (JetBrains), Kotlin 开发, IDE 代码操作。

### 6. [yepcode/mcp-server-js](https://github.com/yepcode/mcp-server-js)

- **描述**: 在安全可扩展的沙盒环境中执行 LLM 生成的代码，并用 JS/Python 创建自定义 MCP 工具。

- **备注**: 官方实现 (YepCode) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 安全代码执行，自定义工具。

### 7. [yzfly/mcp-python-interpreter](https://github.com/yzfly/mcp-python-interpreter)

- **描述**: 安全、标准化的 Python 环境，支持代码执行、环境和包管理。

- **备注**: 社区标杆, 轻量级 Python 执行环境, 适合开发和数据分析。

### 8. [admica/FileScopeMCP](https://github.com/admica/FileScopeMCP)

- **描述**: 分析代码库依赖关系，生成图表，帮助 AI 理解项目结构。

- **备注**: 社区实现, 多语言 (Py 🐍/TS 📇/Rust 🦀), 代码结构分析。

### 9. [mem0ai/mem0-mcp](https://github.com/mem0ai/mem0-mcp)

- **描述**: 管理代码偏好和模式，支持语义搜索，方便在 IDE 中存取技术文档。 (Mem0 官方)

- **备注**: 官方实现 (Mem0 AI) 🎖️, Python 开发 🐍, 本地运行 🏠, 程序员的记忆助手和偏好管理。

### 10. [code-executor](https://github.com/bazinga012/mcp_code_executor)

- **描述**: 允许 AI 在指定的 Conda 环境中执行 Python 代码。

- **备注**: 社区实现, Python 开发, Conda 环境代码执行。

### 11. [code-sandbox-mcp](https://github.com/Automata-Labs-team/code-sandbox-mcp)

- **描述**: 创建安全的 Docker 容器环境来执行代码。

- **备注**: 社区实现, Python 开发, Docker 沙盒代码执行。

### 12. [knowlyr-sandbox](https://github.com/liuxiaotong/knowlyr-agent/tree/main/packages/sandbox)

- **描述**: Code Agent 执行沙箱 — Docker 隔离、文件捕获、超时控制，为 LLM 代码代理提供安全的运行环境。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Docker 沙箱执行。

### 13. [ForeverVM](https://github.com/jamsocket/forevervm/tree/main/javascript/mcp-server)

- **描述**: 在代码沙盒中运行 Python 代码。

- **备注**: 官方实现 (Jamsocket), JavaScript 开发, 代码沙盒。

### 14. [Riza](https://github.com/riza-io/riza-mcp)

- **描述**: Riza 提供的任意代码执行和工具使用平台。

- **备注**: 官方实现 (Riza), Go 开发, 通用代码执行平台。

### 15. [Roundtable](https://github.com/askbudi/roundtable)

- **描述**: 统一AI编程助手的零配置MCP服务器，专为自主代理开发设计，简化多AI工具集成工作流程。

- **备注**: 社区实现 🌟, Python 开发 🐍, 本地/云端部署 🏠☁️, pip install roundtable-ai

### 16. [Semgrep](https://github.com/semgrep/mcp)

- **描述**: 让 AI 代理使用 Semgrep 进行代码安全扫描。 (Semgrep 官方)

- **备注**: 官方实现 (Semgrep) 🎖️, TypeScript 开发 📇, 代码安全扫描 ☁️. (注意: 列表有重复, 一个Py一个TS)

### 17. [ZenML](https://github.com/zenml-io/mcp-zenml)

- **描述**: 与 ZenML MLOps/LLMOps 平台交互，管理机器学习流程。 (ZenML 官方)

- **备注**: 官方实现 (ZenML) 🎖️, Python 开发 🐍, 本地/云端 🏠☁️, MLOps 流程管理。

### 18. [vivekVells/mcp-pandoc](https://github.com/vivekVells/mcp-pandoc)

- **描述**: 使用 Pandoc 进行无缝文档格式转换（Markdown, HTML, PDF, DOCX, CSV 等）。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 文档格式转换。

### 19. [oraios/serena](https://github.com/oraios/serena)

- **描述**: 功能齐全的编码代理，依赖于使用语言服务器的符号化代码操作。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 编码代理。

### 20. [ezyang/codemcp](https://github.com/ezyang/codemcp)

- **描述**: 具有基本读、写和命令行工具的编码代理。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 编码代理。

### 21. [wonderwhy-er/DesktopCommanderMCP](https://github.com/wonderwhy-er/DesktopCommanderMCP)

- **描述**: 增强的文件系统和搜索工具，以及特定于编码的命令和提示。(也含命令行功能)

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 跨平台 🍎🪟🐧, 编码/文件/命令行工具。

### 22. [maxim-saplin/mcp_safe_local_python_executor](https://github.com/maxim-saplin/mcp_safe_local_python_executor)

- **描述**: 基于 HF Smolagents `LocalPythonExecutor` 的安全 Python 解释器。

- **备注**: 社区实现, Python 开发, 本地安全 Python 执行。

### 23. [tumf/mcp-text-editor](https://github.com/tumf/mcp-text-editor)

- **描述**: 面向行的文本文件编辑器。针对 LLM 工具优化，通过高效的部分文件访问最小化 Token 使用。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 文本编辑。

### 24. [VSCode Devtools](https://github.com/biegehydra/BifrostMCP)

- **描述**: 连接到 VSCode IDE 并使用语义工具，如 `find_usages`。

- **备注**: 社区实现, TypeScript 开发 📇, VSCode 集成。

### 25. [xzq.xu/jvm-mcp-server](https://github.com/xzq-xu/jvm-mcp-server)

- **描述**: 基于 JVM 的 MCP 服务器实现项目。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, JVM 集成。

### 26. [yWorks/mcp-typescribe](https://github.com/yWorks/mcp-typescribe)

- **描述**: 高效地向代理提供 TypeScript API 信息，使其能够处理未经训练的 API。

- **备注**: 官方实现 (yWorks), TypeScript 开发 📇, 本地运行 🏠, TypeScript API 信息。

### 27. [zcaceres/fetch-mcp](https://github.com/zcaceres/fetch-mcp)

- **描述**: 灵活获取 JSON、文本和 HTML 数据的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 数据获取。

### 28. [idosal/git-mcp](https://github.com/idosal/git-mcp)

- **描述**: 通用远程 MCP 服务器，用于连接任何 GitHub 仓库或项目以获取文档。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 远程 GitHub 文档访问 ([gitmcp.io](https://gitmcp.io/))。

### 29. [tgeselle/bugsnag-mcp](https://github.com/tgeselle/bugsnag-mcp)

- **描述**: 用于与 Bugsnag 交互的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Bugsnag 集成。

### 30. [jordandalton/restcsv-mcp-server](https://github.com/JordanDalton/RestCsvMcpServer)

- **描述**: 用于 CSV 文件的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, CSV 处理。

### 31. [jjsantos01/jupyter-notebook-mcp](https://github.com/jjsantos01/jupyter-notebook-mcp)

- **描述**: 将 Jupyter Notebook 连接到 Claude AI，允许 Claude 直接交互和控制 Jupyter。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Jupyter 集成。

### 32. [Lstmxx/yapi-mcp-server](https://github.com/Lstmxx/yapi-mcp-server)

- **描述**: 一个用 LLM 将 Yapi 的 API 定义自动化生成为 TypeScript 代码的MCP服务

- **备注**: 社区实现, TypeScript 开发 📇,本地运行 🏠

### 33. [tersePrompts/jarp-mcp](https://github.com/tersePrompts/jarp-mcp)

- **描述**: Java Archive Reader Protocol - 为 AI 代理提供对 Maven 依赖中反编译 Java 代码的即时访问，如同为 AI 装上"X 光透视眼"。

- **备注**: 社区实现 🌟, Node.js/Java 开发 ☕🟢, 本地运行 🏠, Java 类分析与反编译, CFR 内置, 智能缓存

### 34. [tersePrompts/fastMCP4J](https://github.com/tersePrompts/fastMCP4J)

- **描述**: Java 语言构建 MCP 服务器的轻量级注解驱动框架，JSON Schema 2020-12 兼容，安全、快速、零配置。

- **备注**: 社区实现 🌟, Java 开发 ☕, 本地运行 🏠, 注解驱动, 12 个依赖, 支持异步、内存、任务、文件操作

---

## 🖥️ 命令行与 Shell 交互

让 AI 能够执行命令行指令、与 Shell 交互

### 1. [iTerm MCP](https://github.com/ferrislucas/iterm-mcp)

- **描述**: 集成 macOS 的 iTerm2 终端，让 AI 执行和监控终端命令。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, macOS 终端控制 🍎。

### 2. [Windows CLI](https://github.com/SimonB97/win-cli-mcp-server)

- **描述**: 在 Windows 系统上安全执行命令行（PowerShell, CMD, Git Bash）。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Windows 命令行控制 🪟。

### 3. [g0t4/mcp-server-commands](https://github.com/g0t4/mcp-server-commands)

- **描述**: 使用 `run_command` 和 `run_script` 工具运行任何命令。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 通用命令执行。

### 4. [MladenSU/cli-mcp-server](https://github.com/MladenSU/cli-mcp-server)

- **描述**: 具有安全执行和可自定义安全策略的命令行接口。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 安全命令行执行。

### 5. [OthmaneBlial/term_mcp_deepseek](https://github.com/OthmaneBlial/term_mcp_deepseek)

- **描述**: 用于终端的 DeepSeek 类 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 终端交互。

### 6. [tumf/mcp-shell-server](https://github.com/tumf/mcp-shell-server)

- **描述**: 实现模型上下文协议 (MCP) 的安全 Shell 命令执行服务器。

- **备注**: 社区实现, Python 开发, 安全 Shell 执行。

### 7. [wonderwhy-er/DesktopCommanderMCP](https://github.com/wonderwhy-er/DesktopCommanderMCP)

- **描述**: 多功能工具，可管理/执行程序，读/写/搜索/编辑代码和文本文件。(也含代码/文件功能)

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 跨平台 🍎🪟🐧, 命令行/文件/程序管理。

---

## 🔄 版本控制 (Git / GitHub / GitLab)

让 AI 能够操作代码仓库、管理 Pull Request、处理 Issues 等

### 1. [github/github-mcp-server](https://github.com/github/github-mcp-server)

- **描述**: GitHub 官方出品，让 AI 通过 API 深度集成 GitHub，实现自动化工作流等。

- **备注**: 官方实现 (GitHub), Go 开发 🏎️。功能全面，推荐 Docker 部署。

### 2. [Gitee](https://github.com/oschina/mcp-gitee)

- **描述**: Gitee 官方集成，管理 Gitee 仓库、Issues 和 Pull Requests。

- **备注**: 官方实现 (Gitee/oschina) 🎖️, Go 开发 🏎️, 云端/本地 ☁️🏠, Gitee 用户必备。

### 3. [gitea/gitea-mcp](https://gitea.com/gitea/gitea-mcp)

- **描述**: Gitea 官方集成，通过 MCP 与 Gitea 实例交互。

- **备注**: 官方实现 (Gitea) 🎖️, Go 开发 🏎️, 云端/本地 ☁️🏠, 跨平台 🍎🪟🐧, Gitea 集成。

### 4. [modelcontextprotocol/server-github](https://github.com/modelcontextprotocol/servers/tree/main/src/github)

- **描述**: 官方参考实现，集成 GitHub API，管理仓库、文件、PR 和 Issues。

- **备注**: 官方参考, TypeScript 开发 📇, 云服务 ☁️, GitHub 重度用户必备。

### 5. [modelcontextprotocol/server-git](https://github.com/modelcontextprotocol/servers/tree/main/src/git)

- **描述**: 官方参考实现，直接操作本地 Git 仓库，进行读取、搜索和分析。

- **备注**: 官方参考, Python 开发 🐍, 本地运行 🏠, 本地 Git 仓库操作。

### 6. [modelcontextprotocol/server-gitlab](https://github.com/modelcontextprotocol/servers/tree/main/src/gitlab)

- **描述**: 官方参考实现，集成 GitLab API，进行项目管理和 CI/CD 操作。

- **备注**: 官方参考, TypeScript 开发 📇, 云端/本地 ☁️🏠, GitLab 用户适用。

### 7. [adhikasp/mcp-git-ingest](https://github.com/adhikasp/mcp-git-ingest)

- **描述**: 使用 LLM 读取和分析 GitHub 仓库。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, GitHub 仓库分析。

### 8. [ddukbg/github-enterprise-mcp](https://github.com/ddukbg/github-enterprise-mcp)

- **描述**: 用于 GitHub Enterprise API 集成的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云端/本地 ☁️🏠, GitHub Enterprise 集成。

### 9. [kopfrechner/gitlab-mr-mcp](https://github.com/kopfrechner/gitlab-mr-mcp)

- **描述**: 无缝地与 GitLab 项目的 Issues 和 Merge Requests 交互。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, GitLab Issues/MR 操作。

### 10. [Github Actions](https://github.com/ko1ynnky/github-actions-mcp-server)

- **描述**: 与 Github Actions 交互，管理工作流。

- **备注**: 社区实现, TypeScript 开发, GitHub Actions 管理。

### 11. [Tiberriver256/mcp-server-azure-devops](https://github.com/Tiberriver256/mcp-server-azure-devops)

- **描述**: 用于仓库管理、工作项和流水线的 Azure DevOps 集成。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Azure DevOps 集成。

---

## 🗄️ 数据库交互

让 AI 能够查询数据库、检查表结构、甚至修改数据

### 1. [Alibaba Cloud AnalyticDB for MySQL](https://github.com/aliyun/alibabacloud-adb-mysql-mcp-server)

- **描述**: 阿里云 AnalyticDB for MySQL 官方集成，连接 AnalyticDB for MySQL 集群进行数据库元数据查询和数据分析。

- **备注**: 官方实现 (Alibaba Cloud) 🎖️, 阿里云数据库服务。

### 2. [Alibaba Cloud AnalyticDB for PostgreSQL](https://github.com/aliyun/alibabacloud-adbpg-mcp-server)

- **描述**: 阿里云 AnalyticDB for PostgreSQL 官方集成，连接 AnalyticDB for PostgreSQL 实例，查询和分析数据。

- **备注**: 官方实现 (Alibaba Cloud) 🎖️, 阿里云 PostgreSQL 服务。

### 3. [Aiven](https://github.com/Aiven-Open/mcp-aiven)

- **描述**: Aiven 官方集成，导航 Aiven 项目，与 PostgreSQL®, Kafka®, ClickHouse®, OpenSearch® 服务交互。

- **备注**: 官方实现 (Aiven) 🎖️, Python 开发 🐍, 云服务 ☁️, Aiven 云数据库管理。

### 4. [ClickHouse/mcp-clickhouse](https://github.com/ClickHouse/mcp-clickhouse)

- **描述**: ClickHouse 官方集成，连接 ClickHouse 数据库进行查询和模式检查。

- **备注**: 官方实现 (ClickHouse) 🎖️, Python 开发 🐍, 云服务 ☁️, ClickHouse 数据分析利器。

### 5. [Chroma](https://github.com/chroma-core/chroma-mcp)

- **描述**: Chroma 官方集成，用于嵌入、向量搜索、文档存储和全文搜索。

- **备注**: 官方实现 (Chroma) 🎖️, Python 开发 🐍, 本地/云端 🏠☁️, AI 应用数据库，向量搜索。

### 6. [confluentinc/mcp-confluent](https://github.com/confluentinc/mcp-confluent)

- **描述**: Confluent 集成，与 Confluent Kafka 和 Confluent Cloud REST API 交互。

- **备注**: 官方实现 (Confluent) 🎖️, Python 开发 🐍, 云服务 ☁️, Kafka 集成。

### 7. [fireproof-storage/mcp-database-server](https://github.com/fireproof-storage/mcp-database-server)

- **描述**: Fireproof 官方集成，不可变账本数据库，支持实时同步。

- **备注**: 官方实现 (Fireproof) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 分布式数据库同步。

### 8. [googleapis/genai-toolbox](https://github.com/googleapis/genai-toolbox)

- **描述**: Google 官方开源 MCP 服务器，专注于为数据库提供简单、快速、安全的工具。

- **备注**: 官方实现 (Google) 🎖️, Go 开发 🏎️, 云服务 ☁️, Google Cloud 数据库工具。

### 9. [GreptimeDB](https://github.com/GreptimeTeam/greptimedb-mcp-server)

- **描述**: GreptimeDB 官方集成，让 AI 安全地探索和分析 GreptimeDB 中的时序数据。

- **备注**: 官方实现 (Greptime) 🎖️, Python 开发 🐍, 本地运行 🏠, GreptimeDB 时序数据分析。

### 10. [Milvus](https://github.com/zilliztech/mcp-server-milvus)

- **描述**: Zilliz/Milvus 官方集成，搜索、查询和交互 Milvus 向量数据库中的数据。

- **备注**: 官方实现 (Zilliz/Milvus) 🎖️, Python 开发 🐍, 本地/云端 🏠☁️, Milvus 向量数据库操作。

### 11. [MotherDuck](https://github.com/motherduckdb/mcp-server-motherduck)

- **描述**: MotherDuck 官方集成，使用 MotherDuck 和本地 DuckDB 查询和分析数据。

- **备注**: 官方实现 (MotherDuck), Python 开发, DuckDB 云服务交互。

### 12. [Neo4j](https://github.com/neo4j-contrib/mcp-neo4j/)

- **描述**: Neo4j 官方贡献，操作 Neo4j 图数据库（模式+读写 Cypher），并提供图数据库支持的记忆功能。

- **备注**: 官方贡献 (Neo4j) 🎖️, Python 开发 🐍, 本地运行 🏠, 图数据库操作和记忆。

### 13. [Neon](https://github.com/neondatabase/mcp-server-neon)

- **描述**: Neon 官方集成，与 Neon 无服务器 Postgres 平台交互，创建和管理数据库。

- **备注**: 官方实现 (Neon) 🎖️, TypeScript 开发 📇, 云服务 ☁️, Neon Serverless PG 管理。

### 14. [niledatabase/nile-mcp-server](https://github.com/niledatabase/nile-mcp-server)

- **描述**: Nile 的 Postgres 平台 MCP 服务器 - 使用 LLM 管理和查询 Postgres 数据库、租户、用户、认证。

- **备注**: 官方实现 (Nile) 🎖️, Python 开发, Nile PG 平台管理。

### 15. [Qdrant](https://github.com/qdrant/mcp-server-qdrant/)

- **描述**: Qdrant 官方集成，基于 Qdrant 向量搜索引擎实现语义记忆层。

- **备注**: 官方实现 (Qdrant) 🎖️, Python 开发 🐍, 本地运行 🏠, Qdrant 向量搜索与记忆。

### 16. [SingleStore](https://github.com/singlestore-labs/mcp-server-singlestore)

- **描述**: SingleStore 官方集成，与 SingleStore 数据库平台交互。

- **备注**: 官方实现 (SingleStore), Python 开发, SingleStore 数据库操作。

### 17. [StarRocks](https://github.com/StarRocks/mcp-server-starrocks)

- **描述**: StarRocks 官方集成，与 StarRocks 数据库交互。

- **备注**: 官方实现 (StarRocks), Python 开发, StarRocks 数据仓库交互。

### 18. [supabase-community/supabase-mcp](https://github.com/supabase-community/supabase-mcp)

- **描述**: Supabase 官方 MCP 服务器，将 AI 助手直接连接到你的 Supabase 项目，允许执行任务如管理表、获取配置和查询数据。

- **备注**: 官方实现 (Supabase Community) 🎖️, TypeScript 开发 📇, 云服务 ☁️, Supabase 项目管理与查询。

### 19. [Tinybird](https://github.com/tinybirdco/mcp-tinybird)

- **描述**: Tinybird 官方集成，与 Tinybird 无服务器 ClickHouse 平台交互 (查询和 API 能力)。

- **备注**: 官方实现 (Tinybird) 🎖️, Python 开发 🐍, 云服务 ☁️, Tinybird 平台交互。

### 20. [weaviate/mcp-server-weaviate](https://github.com/weaviate/mcp-server-weaviate)

- **描述**: 连接到 Weaviate 集合作为知识库，并将 Weaviate 用作聊天记忆存储的 MCP 服务器。

- **备注**: 官方实现 (Weaviate) 🎖️, Python/TypeScript 开发 🐍📇, 云服务 ☁️, Weaviate 知识库/记忆。

### 21. [modelcontextprotocol/server-postgres](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres)

- **描述**: 官方参考实现，集成 PostgreSQL，支持查询和模式分析。

- **备注**: 官方参考, TypeScript 开发 📇, 本地运行 🏠, PostgreSQL 数据库操作。

### 22. [modelcontextprotocol/server-redis](https://github.com/modelcontextprotocol/servers/tree/main/src/redis)

- **描述**: 官方参考实现，与 Redis 键值存储进行交互。

- **备注**: 官方参考, TypeScript 开发, Redis 缓存/存储操作。

### 23. [modelcontextprotocol/server-sqlite](https://github.com/modelcontextprotocol/servers/tree/main/src/sqlite)

- **描述**: 官方参考实现，操作 SQLite 数据库，并内置商业智能能力。

- **备注**: 官方参考, Python 开发 🐍, 本地运行 🏠, 本地 SQLite 数据库操作。

### 24. [DBHub](https://github.com/bytebase/dbhub/)

- **描述**: 通用数据库 MCP 服务器，可连接 MySQL, PostgreSQL, SQLite, DuckDB 等。

- **备注**: 社区实现 (Bytebase) 🎖️, TypeScript 开发 📇, 本地运行 🏠, 多种数据库支持。

### 25. [alexanderzuev/supabase-mcp-server](https://github.com/alexander-zuev/supabase-mcp-server)

- **描述**: Supabase MCP 服务器，支持 SQL 查询执行和数据库探索工具。

- **备注**: 社区实现, Supabase 集成。

### 26. [aliyun/alibabacloud-tablestore-mcp-server](https://github.com/aliyun/alibabacloud-tablestore-mcp-server)

- **描述**: 阿里云 Tablestore MCP 服务，功能包括添加文档、基于向量和标量的文档语义搜索、RAG 友好、Serverless。

- **备注**: 官方实现 (Alibaba Cloud) 🎖️, Java/Python 开发 ☕🐍, 云服务 ☁️, 阿里云 Tablestore。

### 27. [benborla29/mcp-server-mysql](https://github.com/benborla/mcp-server-mysql)

- **描述**: NodeJS 中的 MySQL 数据库集成，具有可配置的访问控制和模式检查。

- **备注**: 社区实现, Node.js 开发, 云端/本地 ☁️🏠, MySQL 集成 (Node.js)。

### 28. [c4pt0r/mcp-server-tidb](https://github.com/c4pt0r/mcp-server-tidb)

- **描述**: TiDB 数据库集成，具有模式检查和查询能力。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, TiDB 集成。

### 29. [Canner/wren-engine](https://github.com/Canner/wren-engine)

- **描述**: 面向 MCP 客户端和 AI Agents 的语义引擎。

- **备注**: 社区实现, Python/Rust 开发 🐍🦀, 本地运行 🏠, 语义引擎。

### 30. [centralmind/gateway](https://github.com/centralmind/gateway)

- **描述**: MCP 和 MCP SSE 服务器，根据数据库模式和数据自动生成 API。支持 PG, Clickhouse, MySQL, Snowflake, BigQuery, Supabase。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, 跨平台 🍎🪟, 数据库 API 自动生成。

### 31. [cr7258/elasticsearch-mcp-server](https://github.com/cr7258/elasticsearch-mcp-server)

- **描述**: 提供 Elasticsearch 交互的 MCP 服务器实现。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Elasticsearch 集成。

### 32. [Dataring-engineering/mcp-server-trino](https://github.com/Dataring-engineering/mcp-server-trino)

- **描述**: Trino MCP 服务器，用于从 Trino 集群查询和访问数据。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Trino 集成。

### 33. [designcomputer/mysql_mcp_server](https://github.com/designcomputer/mysql_mcp_server)

- **描述**: Python 实现的 MySQL 集成，带访问控制和模式检查。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, MySQL 数据库操作。

### 34. [domdomegg/airtable-mcp-server](https://github.com/domdomegg/airtable-mcp-server)

- **描述**: 读写 Airtable 数据库，带模式检查。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Airtable 读写。

### 35. [edwinbernadus/nocodb-mcp-server](https://github.com/edwinbernadus/nocodb-mcp-server)

- **描述**: Nocodb 数据库集成，读写能力。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Nocodb 集成。

### 36. [ergut/mcp-bigquery-server](https://github.com/ergut/mcp-bigquery-server)

- **描述**: Google BigQuery 集成的服务器实现，支持直接访问和查询。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, BigQuery 集成 (TS)。

### 37. [f4ww4z/mcp-mysql-server](https://github.com/f4ww4z/mcp-mysql-server)

- **描述**: 基于 Node.js 的 MySQL 数据库集成，提供安全的数据库操作。

- **备注**: 社区实现, Node.js 开发, 本地运行 🏠, MySQL 集成 (Node.js)。

### 38. [FreePeak/db-mcp-server](https://github.com/FreePeak/db-mcp-server)

- **描述**: 高性能多数据库 MCP 服务器 (Go)，支持 MySQL & PG (NoSQL 即将推出)。含查询、事务、模式探索等工具。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, 多数据库支持 (Go)。

### 39. [furey/mongodb-lens](https://github.com/furey/mongodb-lens)

- **描述**: 功能齐全的 MongoDB 数据库 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, MongoDB 高级操作。

### 40. [gannonh/firebase-mcp](https://github.com/gannonh/firebase-mcp)

- **描述**: Firebase 服务，包括 Auth、Firestore 和 Storage。

- **备注**: 社区实现, Firebase 集成 🔥, 云服务 ☁️.

### 41. [get-convex/convex-backend](https://stack.convex.dev/convex-mcp-server)

- **描述**: Convex 数据库集成，用于内省表、函数和运行一次性查询。

- **备注**: 官方实现 (Convex) 🎖️, TypeScript 开发 📇, 云服务 ☁️, Convex 集成。 ([Source](https://github.com/get-convex/convex-backend/blob/main/npm-packages/convex/src/cli/mcp.ts))

### 42. [hannesrudolph/sqlite-explorer-fastmcp-mcp-server](https://github.com/hannesrudolph/sqlite-explorer-fastmcp-mcp-server)

- **描述**: 提供对 SQLite 数据库安全只读访问的 MCP 服务器 (FastMCP)。LLM 可探索查询，带安全特性和查询验证。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, SQLite 安全只读访问 (FastMCP)。

### 43. [idoru/influxdb-mcp-server](https://github.com/idoru/influxdb-mcp-server)

- **描述**: 对 InfluxDB OSS API v2 执行查询。

- **备注**: 社区实现, TypeScript 开发 📇, 云端/本地 ☁️🏠, InfluxDB 查询。

### 44. [isaacwasserman/mcp-snowflake-server](https://github.com/isaacwasserman/mcp-snowflake-server)

- **描述**: Snowflake 集成，实现读和（可选）写操作以及洞察跟踪。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Snowflake 集成。

### 45. [joshuarileydev/supabase-mcp-server](https://github.com/joshuarileydev/supabase)

- **描述**: 用于在 Supabase 中管理和创建项目及组织的 Supabase MCP 服务器。

- **备注**: 社区实现, Supabase 管理。

### 46. [jovezhong/mcp-timeplus](https://github.com/jovezhong/mcp-timeplus)

- **描述**: Apache Kafka 和 Timeplus 的 MCP 服务器。能列出 Kafka 主题、轮询消息、本地保存数据并通过 Timeplus 用 SQL 查询流数据。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Kafka/Timeplus 集成。

### 47. [KashiwaByte/vikingdb-mcp-server](https://github.com/KashiwaByte/vikingdb-mcp-server)

- **描述**: VikingDB 集成，具有集合和索引介绍、向量存储和搜索能力。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, VikingDB 集成。

### 48. [kiliczsh/mcp-mongo-server](https://github.com/kiliczsh/mcp-mongo-server)

- **描述**: 用于 MongoDB 的模型上下文协议服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, MongoDB 集成 (TS)。

### 49. [ktanaka101/mcp-server-duckdb](https://github.com/ktanaka101/mcp-server-duckdb)

- **描述**: DuckDB 数据库集成，具有模式检查和查询能力。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, DuckDB 集成。

### 50. [BigQuery (by LucasHild)](https://github.com/LucasHild/mcp-server-bigquery)

- **描述**: 让 AI 检查 BigQuery 数据库模式并执行查询。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Google BigQuery 查询。

### 51. [mcp-server-jdbc](https://github.com/quarkiverse/quarkus-mcp-servers/tree/main/jdbc)

- **描述**: 连接到任何兼容 JDBC 的数据库，并执行查询、插入、更新、删除等操作。

- **备注**: 社区实现 (Quarkiverse), Java 开发 ☕, 本地运行 🏠, 通用 JDBC 连接。

### 52. [memgraph/mcp-memgraph](https://github.com/memgraph/mcp-memgraph)

- **描述**: Memgraph MCP 服务器 - 包括对 Memgraph 执行查询和模式资源的工具。

- **备注**: 官方实现 (Memgraph) 🎖️, Python 开发 🐍, 本地运行 🏠, Memgraph 集成。

### 53. [openlink/mcp-server-odbc](https://github.com/OpenLinkSoftware/mcp-odbc-server)

- **描述**: 通过开放数据库连接 (ODBC) 协议实现通用数据库管理系统 (DBMS) 连接的 MCP 服务器。

- **备注**: 社区实现 (OpenLink), Python 开发 🐍, 本地运行 🏠, 通用 ODBC 连接。

### 54. [openlink/mcp-server-sqlalchemy](https://github.com/OpenLinkSoftware/mcp-sqlalchemy-server)

- **描述**: 通过 SQLAlchemy 使用 Python ODBC (pyodbc) 实现通用 DBMS 连接的 MCP 服务器。

- **备注**: 社区实现 (OpenLink), Python 开发 🐍, 本地运行 🏠, 通用 SQLAlchemy 连接 (ODBC)。

### 55. [pab1it0/adx-mcp-server](https://github.com/pab1it0/adx-mcp-server)

- **描述**: 查询和分析 Azure Data Explorer 数据库。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Azure Data Explorer 查询。

### 56. [pab1it0/prometheus-mcp-server](https://github.com/pab1it0/prometheus-mcp-server)

- **描述**: 查询和分析 Prometheus 开源监控系统。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Prometheus 查询。

### 57. [QuantGeekDev/mongo-mcp](https://github.com/QuantGeekDev/mongo-mcp)

- **描述**: MongoDB 集成，使 LLM 能够直接与数据库交互。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, MongoDB 集成 (TS)。

### 58. [rashidazarang/airtable-mcp](https://github.com/rashidazarang/airtable-mcp)

- **描述**: 将 AI 工具直接连接到 Airtable。使用自然语言查询、创建、更新和删除记录。功能包括库管理、表操作等。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Airtable 全功能操作 (Python)。

### 59. [runekaagaard/mcp-alchemy](https://github.com/runekaagaard/mcp-alchemy)

- **描述**: 通用 SQLAlchemy 数据库集成，支持 PG, MySQL, MariaDB, SQLite, Oracle, MS SQL Server 等。含模式/关系检查和大数据集分析能力。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 通用 SQLAlchemy 集成。

### 60. [sirmews/mcp-pinecone](https://github.com/sirmews/mcp-pinecone)

- **描述**: Pinecone 集成，具有向量搜索能力。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Pinecone 向量搜索。

### 61. [TheRaLabs/legion-mcp](https://github.com/TheRaLabs/legion-mcp)

- **描述**: 通用数据库 MCP 服务器，支持 PG, Redshift, CockroachDB, MySQL, RDS MySQL, MS SQL Server, BigQuery, Oracle DB, SQLite。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 多种数据库支持 (Python)。

### 62. [tradercjz/dolphindb-mcp-server](https://github.com/tradercjz/dolphindb-mcp-server)

- **描述**: DolphinDB 数据库集成，具有模式检查和查询能力。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, DolphinDB 集成。

### 63. [XGenerationLab/xiyan_mcp_server](https://github.com/XGenerationLab/xiyan_mcp_server)

- **描述**: 支持使用自然语言查询从数据库获取数据的 MCP 服务器，由 XiyanSQL 作为 text-to-SQL LLM 驱动。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 自然语言转 SQL 查询 (XiyanSQL)。

### 64. [xing5/mcp-google-sheets](https://github.com/xing5/mcp-google-sheets)

- **描述**: 用于与 Google Sheets 交互的模型上下文协议服务器。提供创建、读取、更新和管理电子表格的工具。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Google Sheets 操作。

### 65. [Zhwt/go-mcp-mysql](https://github.com/Zhwt/go-mcp-mysql)

- **描述**: 易于使用、零依赖的 MySQL MCP 服务器 (Go)，具有可配置的只读模式和模式检查。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, MySQL 集成 (Go)。

---

## ☁️ 云平台与服务集成 (AWS, Cloudflare, Azure, K8s, etc.)

让 AI 能够管理云资源、调用云服务 API 等

### 1. [Alibaba Cloud DataWorks](https://github.com/aliyun/alibabacloud-dataworks-mcp-server)

- **描述**: 阿里云 DataWorks 官方集成，通过标准化接口与 DataWorks Open API 进行 AI 交互，用于云资源操作。

- **备注**: 官方实现 (Alibaba Cloud) 🎖️, 阿里云数据平台。

### 2. [AWS MCP Servers](https://github.com/awslabs/mcp)

- **描述**: AWS 官方维护的一组 MCP 服务器合集，通过 Model Context Protocol（MCP）为 AI 助手提供对 AWS 文档、API、基础设施等资源的访问，帮助在任意支持 MCP 的环境中高效使用 AWS。

- **备注**: 官方实现（AWS）🎖️，覆盖 AWS API、文档/最佳实践、基础设施与部署等多类场景，可配合各类 MCP 客户端（IDE、聊天应用等）使用。

### 3. [Cloudflare](https://github.com/cloudflare/mcp-server-cloudflare)

- **描述**: Cloudflare 官方集成，部署、配置和查询 Cloudflare 开发者平台资源 (Workers/KV/R2/D1)。

- **备注**: 官方实现 (Cloudflare) 🎖️, TypeScript 开发 📇, 云服务 ☁️, Cloudflare 平台管理。

### 4. [AWS KB Retrieval](https://github.com/modelcontextprotocol/servers/tree/main/src/aws-kb-retrieval-server)

- **描述**: 官方参考实现，使用 Bedrock Agent Runtime 从 AWS 知识库检索信息。

- **备注**: 官方参考, TypeScript 开发, AWS Bedrock 知识库。

### 5. [AWS S3](https://github.com/aws-samples/sample-mcp-server-s3)

- **描述**: AWS 官方示例，灵活地从 S3 获取对象（如 PDF 文档）。

- **备注**: 官方示例 (AWS), TypeScript 开发, S3 文件获取。

### 6. [VolcEngine TOS](https://github.com/dinghuazhou/sample-mcp-server-tos)

- **描述**: 火山引擎官方示例，灵活地从火山引擎对象存储 (TOS) 获取对象。

- **备注**: 官方示例 (VolcEngine), TypeScript 开发, 火山引擎 TOS 文件获取。

### 7. [alexbakers/mcp-ipfs](https://github.com/alexbakers/mcp-ipfs)

- **描述**: 上传和操作 IPFS 存储。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, IPFS 存储操作。

### 8. [alexei-led/aws-mcp-server](https://github.com/alexei-led/aws-mcp-server)

- **描述**: 轻量级服务器，让 AI 执行 AWS CLI 命令 (带 Unix 管道和模板)，支持 Docker 安全运行 (多架构)。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 通过 CLI 管理 AWS (安全 Docker)。

### 9. [alexei-led/k8s-mcp-server](https://github.com/alexei-led/k8s-mcp-server)

- **描述**: 轻量级服务器，让 AI 安全地执行 Kubernetes CLI 命令 (`kubectl`, `helm`, `istioctl`, `argocd`) (带 Unix 管道)，支持 Docker 安全运行 (多架构)。

- **备注**: 社区实现, Python 开发 🐍, Kubernetes CLI 操作 (安全 Docker)。

### 10. [AWS Resources Operations](https://github.com/baryhuang/mcp-server-aws-resources-python)

- **描述**: 运行生成的 Python 代码以安全地查询或修改任何 boto3 支持的 AWS 资源。

- **备注**: 社区实现, Python 开发, 通过 Boto3 管理 AWS 资源。

### 11. [bright8192/esxi-mcp-server](https://github.com/bright8192/esxi-mcp-server)

- **描述**: 基于 MCP 的 VMware ESXi/vCenter 管理服务器，提供虚拟机管理的简单 REST API 接口。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, VMware ESXi/vCenter 管理。

### 12. [flux159/mcp-server-kubernetes](https://github.com/Flux159/mcp-server-kubernetes)

- **描述**: Kubernetes 集群操作的 TypeScript 实现 (pods, deployments, services)。

- **备注**: 社区实现, TypeScript 开发 📇, 云端/本地 ☁️🏠, Kubernetes 操作 (TS)。

### 13. [hardik-id/azure-resource-graph-mcp-server](https://github.com/hardik-id/azure-resource-graph-mcp-server)

- **描述**: 使用 Azure Resource Graph 大规模查询和分析 Azure 资源的 MCP 服务器，使 AI 助手能探索监控 Azure 基础设施。

- **备注**: 社区实现, TypeScript 开发 📇, 云端/本地 ☁️🏠, Azure Resource Graph 查询。

### 14. [jdubois/azure-cli-mcp](https://github.com/jdubois/azure-cli-mcp)

- **描述**: Azure CLI 命令行包装器，允许直接与 Azure 对话。

- **备注**: 社区实现, Azure CLI 封装。

### 15. [johnneerdael/netskope-mcp](https://github.com/johnneerdael/netskope-mcp)

- **描述**: 提供对 Netskope Private Access 环境中所有组件的访问，包括详细设置信息和 LLM 使用示例。

- **备注**: 社区实现, 云服务 ☁️, Netskope Private Access 集成。

### 16. [Kubernetes (Go)](https://github.com/strowk/mcp-k8s-go)

- **描述**: Go 语言实现的 Kubernetes 服务器，用于浏览 Pods、日志、事件、命名空间等。

- **备注**: 社区实现, Go 开发 🏎️, 云端/本地 ☁️🏠, Kubernetes 集群管理 (Go)。

### 17. [Kubernetes and OpenShift](https://github.com/manusa/kubernetes-mcp-server)

- **描述**: 功能强大的 Kubernetes MCP 服务器，额外支持 OpenShift。提供 CRUD 操作及专用工具。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, Kubernetes/OpenShift 高级管理。

### 18. [nwiizo/tfmcp](https://github.com/nwiizo/tfmcp)

- **描述**: Terraform MCP 服务器，允许 AI 助手管理和操作 Terraform 环境 (读配置/分析计划/应用配置/管理状态)。

- **备注**: 社区实现, Rust 开发 🦀, 本地运行 🏠, Terraform 管理。

### 19. [Pulumi](https://github.com/dogukanakkaya/pulumi-mcp-server)

- **描述**: 与 Pulumi API 交互，创建和列出 Stacks（基础设施即代码）。

- **备注**: 社区实现, Go 开发, Pulumi IaC 管理。

### 20. [rohitg00/kubectl-mcp-server](https://github.com/rohitg00/kubectl-mcp-server)

- **描述**: 用于 Kubernetes 的 MCP 服务器，使 AI 助手能通过自然语言与 K8s 集群交互。

- **备注**: 社区实现, Python 开发 🐍, 云端/本地 ☁️🏠, Kubernetes 自然语言交互。

### 21. [silenceper/mcp-k8s](https://github.com/silenceper/mcp-k8s)

- **描述**: AI 驱动的 Kubernetes 资源管理工具，允许通过自然语言操作 K8s 集群中的任何资源 (原生/CRD)。

- **备注**: 社区实现, Go 开发 🏎️, 云端/本地 ☁️🏠, AI 驱动 K8s 管理。

### 22. [thunderboltsid/mcp-nutanix](https://github.com/thunderboltsid/mcp-nutanix)

- **描述**: 基于 Go 的 MCP 服务器，用于与 Nutanix Prism Central 资源交互。

- **备注**: 社区实现, Go 开发 🏎️, 本地/云端 🏠☁️, Nutanix Prism Central 交互。

### 23. [weibaohui/k8m](https://github.com/weibaohui/k8m)

- **描述**: 提供 MCP 多集群 Kubernetes 管理和操作，带管理界面、日志记录和近 50 个内置工具 (支持标准/CRD)。

- **备注**: 社区实现, Go 开发 🏎️, 云端/本地 ☁️🏠, 多集群 K8s 管理 (带 UI)。

### 24. [weibaohui/kom](https://github.com/weibaohui/kom)

- **描述**: 提供 MCP 多集群 Kubernetes 管理和操作。可作为 SDK 集成到项目中，含近 50 个内置工具 (支持标准/CRD)。

- **备注**: 社区实现, Go 开发 🏎️, 云端/本地 ☁️🏠, 多集群 K8s 管理 (SDK)。

### 25. [wenhuwang/mcp-k8s-eye](https://github.com/wenhuwang/mcp-k8s-eye)

- **描述**: 用于 Kubernetes 管理的 MCP 服务器，分析集群和应用健康状况。

- **备注**: 社区实现, Go 开发 🏎️, 云端/本地 ☁️🏠, K8s 管理与健康分析。

### 26. [erikhoward/adls-mcp-server](https://github.com/erikhoward/adls-mcp-server)

- **描述**: 用于 Azure Data Lake Storage 的 MCP 服务器。可管理容器、读/写/上传/下载文件及管理元数据。

- **备注**: 社区实现, Python 开发 🐍, 云端/本地 ☁️🏠, Azure Data Lake Storage 管理。

---

## 🔍 搜索

让 AI 能够调用各种搜索引擎或专业搜索服务

### 1. [Alibaba Cloud OpenSearch](https://github.com/aliyun/alibabacloud-opensearch-mcp-server)

- **描述**: 阿里云 OpenSearch 官方集成，AI 代理通过标准化接口与 OpenSearch 交互的工具。

- **备注**: 官方实现 (Alibaba Cloud) 🎖️, 阿里云搜索服务。

### 2. [Exa](https://github.com/exa-labs/exa-mcp-server)

- **描述**: Exa 官方集成，使用专为 AI 设计的 Exa 搜索引擎进行搜索。

- **备注**: 官方实现 (Exa) 🎖️, TypeScript 开发 📇, 云服务 ☁️, AI 专用搜索引擎。

### 3. [Kagi Search](https://github.com/kagisearch/kagimcp)

- **描述**: Kagi 官方集成，使用 Kagi 的搜索 API 进行网页搜索。

- **备注**: 官方实现 (Kagi) 🎖️, TypeScript 开发 📇, 云服务 ☁️, Kagi 搜索引擎。 (用户列表为Py, awesome为TS)

### 4. [Perplexity](https://github.com/ppl-ai/modelcontextprotocol)

- **描述**: Perplexity 官方集成，连接 Perplexity Sonar API，实现实时全网研究。

- **备注**: 官方实现 (Perplexity), Python 开发, Perplexity 实时搜索。

### 5. [Search1API](https://github.com/fatwang2/search1api-mcp)

- **描述**: Search1API 官方集成，一个 API 实现搜索、抓取和站点地图功能 (需付费 API Key)。

- **备注**: 官方实现 (Search1API), TypeScript 开发 📇, 云服务 ☁️, 多功能搜索 API。

### 6. [Tavily](https://github.com/tavily-ai/tavily-mcp)

- **描述**: Tavily 官方集成，专为 AI 代理设计的搜索引擎（搜索+提取）。

- **备注**: 官方实现 (Tavily), Python 开发, AI 代理专用搜索引擎。

### 7. [tinyfish-io/agentql-mcp](https://github.com/tinyfish-io/agentql-mcp)

- **描述**: AgentQL MCP 服务器，提供 AgentQL 的数据提取能力。

- **备注**: 官方实现 (TinyFish IO) 🎖️, TypeScript 开发 📇, 云服务 ☁️, AgentQL 数据提取。

### 8. [vectorize-io/vectorize-mcp-server](https://github.com/vectorize-io/vectorize-mcp-server)

- **描述**: Vectorize MCP 服务器，用于高级检索、私有深度研究、任意文件转 Markdown 提取和文本分块。

- **备注**: 官方实现 (Vectorize) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 高级检索/RAG。

### 9. [zoomeye-ai/mcp_zoomeye](https://github.com/zoomeye-ai/mcp_zoomeye)

- **描述**: 通过 ZoomEye MCP 服务器查询网络资产信息。

- **备注**: 官方实现 (ZoomEye), TypeScript 开发 📇, 云服务 ☁️, 网络空间测绘搜索。

### 10. [Brave Search](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search)

- **描述**: 官方参考实现，使用 Brave 的搜索 API 进行网页和本地搜索。

- **备注**: 官方参考, TypeScript 开发 📇, 云服务 ☁️, Brave 搜索引擎。

### 11. [0xdaef0f/job-searchoor](https://github.com/0xDAEF0F/job-searchoor)

- **描述**: 用于搜索职位列表的 MCP 服务器，支持日期、关键词、远程工作选项等筛选。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 职位搜索。

### 12. [ac3xx/mcp-servers-kagi](https://github.com/ac3xx/mcp-servers-kagi)

- **描述**: Kagi 搜索 API 集成 (社区实现版本)。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Kagi 搜索 (社区 TS 版)。

### 13. [andybrandt/mcp-simple-arxiv](https://github.com/andybrandt/mcp-simple-arxiv)

- **描述**: 让 LLM 从 arXiv 搜索和阅读论文的 MCP。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, arXiv 论文搜索。

### 14. [andybrandt/mcp-simple-pubmed](https://github.com/andybrandt/mcp-simple-pubmed)

- **描述**: 让 LLM 从 PubMed 搜索和阅读医学/生命科学论文的 MCP。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, PubMed 论文搜索。

### 15. [angheljf/nyt](https://github.com/angheljf/nyt)

- **描述**: 使用 NYTimes API 搜索文章。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 纽约时报文章搜索。

### 16. [Bigsy/Clojars-MCP-Server](https://github.com/Bigsy/Clojars-MCP-Server)

- **描述**: Clojars MCP 服务器，提供 Clojure 库的最新依赖信息。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Clojure 依赖搜索。

### 17. [blazickjp/arxiv-mcp-server](https://github.com/blazickjp/arxiv-mcp-server)

- **描述**: 搜索 ArXiv 研究论文。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, ArXiv 搜索 (另一版本)。

### 18. [chanmeng/google-news-mcp-server](https://github.com/ChanMeng666/server-google-news)

- **描述**: Google News 集成，自动主题分类，多语言支持，全面搜索能力 (SerpAPI)。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Google News 搜索 (SerpAPI)。

### 19. [ConechoAI/openai-websearch-mcp](https://github.com/ConechoAI/openai-websearch-mcp)

- **描述**: 提供 OpenAI `web_search` 内置工具的 Python MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地/云端 🏠☁️, OpenAI 网页搜索模拟。

### 20. [devflowinc/trieve](https://github.com/devflowinc/trieve/tree/main/clients/mcp-server)

- **描述**: 通过 Trieve 爬取、嵌入、分块、搜索和检索数据集信息。

- **备注**: 官方实现 (Trieve) 🎖️, TypeScript 开发 📇, 云端/本地 🏠☁️, Trieve RAG 平台。

### 21. [Dumpling-AI/mcp-server-dumplingai](https://github.com/Dumpling-AI/mcp-server-dumplingai)

- **描述**: 访问 Dumpling AI 提供的数据、网页抓取和文档转换 API。

- **备注**: 官方实现 (Dumpling AI) 🎖️, TypeScript 开发 📇, 云服务 ☁️, Dumpling AI API 集成。

### 22. [erithwik/mcp-hn](https://github.com/erithwik/mcp-hn)

- **描述**: 用于搜索 Hacker News、获取头条等的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Hacker News 搜索。

### 23. [genomoncology/biomcp](https://github.com/genomoncology/biomcp)

- **描述**: 生物医学研究服务器，提供对 PubMed、ClinicalTrials.gov 和 MyVariant.info 的访问。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 生物医学信息搜索。

### 24. [Google Custom Search](https://github.com/adenot/mcp-google-search)

- **描述**: 通过 Google 自定义搜索 API 提供 Google 搜索结果。

- **备注**: 社区实现, TypeScript 开发, Google 自定义搜索。

### 25. [hellokaton/unsplash-mcp-server](https://github.com/hellokaton/unsplash-mcp-server)

- **描述**: 用于 Unsplash 图片搜索的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Unsplash 图片搜索。

### 26. [Ihor-Sokoliuk/MCP-SearXNG](https://github.com/ihor-sokoliuk/mcp-searxng)

- **描述**: 连接到 SearXNG 元搜索引擎实例。

- **备注**: 社区实现, TypeScript 开发 📇, 本地/云端 🏠☁️, SearXNG 元搜索。

### 27. [isnow890/naver-search-mcp](https://github.com/isnow890/naver-search-mcp)

- **描述**: Naver 搜索 API 集成 MCP 服务器，支持博客、新闻、购物搜索和 DataLab 分析功能。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Naver 搜索 (韩国)。

### 28. [Bing Web Search API](https://github.com/leehanchung/bing-search-mcp)

- **描述**: 微软必应网页搜索 API 的服务器实现。

- **备注**: 社区实现, Python 开发 🐍, Bing 搜索。 (Awesome列表为TS, 用户列表为Py, 可能有多个实现)

### 29. [kshern/mcp-tavily](https://github.com/kshern/mcp-tavily.git)

- **描述**: Tavily AI 搜索 API (社区实现版本)。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Tavily 搜索 (社区 TS 版)。

### 30. [mzxrai/mcp-webresearch](https://github.com/mzxrai/mcp-webresearch)

- **描述**: 搜索 Google 并在任何主题上进行深度网络研究。

- **备注**: 社区实现, 搜索与研究。

### 31. [nickclyde/duckduckgo-mcp-server](https://github.com/nickclyde/duckduckgo-mcp-server)

- **描述**: 使用 DuckDuckGo 进行网页搜索。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, DuckDuckGo 搜索 (Python)。

### 32. [pskill9/web-search](https://github.com/pskill9/web-search)

- **描述**: 无需 API Key，使用 Google 搜索结果进行免费网页搜索的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 免费 Google 搜索。

### 33. [reading-plus-ai/mcp-server-deep-research](https://github.com/reading-plus-ai/mcp-server-deep-research)

- **描述**: 提供类 OpenAI/Perplexity 自主深度研究、结构化查询细化和简洁报告的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 自主深度研究。

### 34. [SecretiveShell/MCP-searxng](https://github.com/SecretiveShell/MCP-searxng)

- **描述**: 连接到 searXNG 实例的 MCP 服务器 (社区实现版本)。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, SearXNG 元搜索 (Python)。

### 35. [takashiishida/arxiv-latex-mcp](https://github.com/takashiishida/arxiv-latex-mcp)

- **描述**: 获取 arXiv 论文的 LaTeX 源码，以处理数学内容和公式。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, arXiv LaTeX 源码获取。

### 36. [the0807/GeekNews-MCP-Server](https://github.com/the0807/GeekNews-MCP-Server)

- **描述**: 检索和处理来自 GeekNews 网站新闻数据的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, GeekNews 新闻获取。

### 37. [Tomatio13/mcp-server-tavily](https://github.com/Tomatio13/mcp-server-tavily)

- **描述**: Tavily AI 搜索 API (社区实现版本)。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Tavily 搜索 (社区 Py 版)。

### 38. [zhsama/duckduckgo-mcp-server](https://github.com/zhsama/duckduckgo-mpc-server)

- **描述**: 提供 DuckDuckGo 搜索功能的基于 TypeScript 的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地/云端 🏠☁️, DuckDuckGo 搜索 (TypeScript)。

### 39. [mcp-local-rag](https://github.com/nkapila6/mcp-local-rag)

- **描述**: 本地运行的 RAG 式网页搜索，使用 MediaPipe Embedder 和 DuckDuckGo。

- **备注**: 社区实现, Python 开发, 本地 RAG 搜索 (无需 API Key)。

### 40. [douyin-mcp-server](https://github.com/yzfly/douyin-mcp-server)

- **描述**: 提取抖音无水印视频链接，视频文案，douyin-mcp-server

- **备注**: 社区实现, Python 开发, API 默认使用 [SiliconFlow API](https://cloud.siliconflow.cn/i/TxUlXG3u)

### 41. [Aas-ee/open-webSearch](https://github.com/Aas-ee/open-webSearch)

- **描述**: 一个基于多引擎搜索结果的模型上下文协议(MCP)服务器，支持免费网络搜索，无需API密钥。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 云服务 ☁️ , 支持 Bing, Baidu, DuckDuckGo, Brave, Exa, Github, and CSDN.

### 42. [Multi-Source Media MCP Server (M3S)](https://github.com/Decade-qiu/Multi-Source-Media-MCP-Server)

- **描述**: 多源媒体聚合与生成，统一访问 Unsplash/Pexels、Web 爬取媒体，支持多后端 AI 图像生成以及全网图片爬虫。

- **备注**: 原生 Go ✨，本地运行 🏠，支持多平台媒体 API 和 AI 图像生成、爬虫扩展。

### 43. [MLT-OSS/FirstData](https://github.com/MLT-OSS/FirstData)

- **描述**: 全球最全面的权威数据源知识库，132+ 经验证数据源（政府、国际组织、学术机构），帮助 AI 减少幻觉。提供结构化元数据、100% URL 验证、中英双语支持。目标：1000+ 数据源。

- **备注**: 本地/云端 🏠☁️，中国数据源深度覆盖 🇨🇳，AI 事实防线，抗幻觉数据底座。

---

## 💬 通讯与协作 (Slack, Email, Calendar, Social, etc.)

让 AI 能够收发消息、管理日程、参与团队协作等

### 1. [agentmail-toolkit/mcp](https://github.com/agentmail-to/agentmail-toolkit/tree/main/mcp)

- **描述**: 用于即时创建收件箱以发送、接收和处理邮件的 MCP 服务器。专为 AI Agents 设计的邮件服务。

- **备注**: 官方实现 (AgentMail) 🎖️, Python 开发 🐍, 邮件处理。

### 2. [Inbox Zero](https://github.com/elie222/inbox-zero/tree/main/apps/mcp-server)

- **描述**: Inbox Zero 官方集成，AI 个人邮件助手 (基于 Gmail，提供需回复/需跟进邮件识别等功能)。

- **备注**: 官方实现 (Inbox Zero) 🎖️, Python 开发 🐍, 云服务 ☁️, 智能邮件管理。

### 3. [gotoHuman](https://github.com/gotohuman/gotohuman-mcp-server)

- **描述**: gotoHuman 官方集成，允许 AI 代理和自动化向人类发送请求以供批准。

- **备注**: 官方实现 (gotoHuman), TypeScript 开发, 人机协作审批。

### 4. [InditexTech/mcp-teams-server](https://github.com/InditexTech/mcp-teams-server)

- **描述**: 集成 Microsoft Teams 消息传递 (读/发/提及/列成员/线程) 的 MCP 服务器。

- **备注**: 社区实现 (InditexTech), Python 开发 🐍, 云服务 ☁️, Microsoft Teams 集成。

### 5. [modelcontextprotocol/server-bluesky](https://github.com/keturiosakys/bluesky-context-server)

- **描述**: Bluesky 实例集成，用于查询和交互。

- **备注**: 官方参考 (推测, 在 MCP org 下), TypeScript 开发 📇, 云服务 ☁️, Bluesky 社交集成。

### 6. [modelcontextprotocol/server-slack](https://github.com/modelcontextprotocol/servers/tree/main/src/slack)

- **描述**: 官方参考实现，集成 Slack，AI 能管理频道、发消息。

- **备注**: 官方参考, TypeScript 开发 📇, 云服务 ☁️, Slack 团队协作。

### 7. [softeria/ms-365-mcp-server](https://github.com/softeria/ms-365-mcp-server)

- **描述**: 连接整个 Microsoft 365 套件 (Graph API)，包括邮件、文件、Excel、日历等的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Microsoft 365 全家桶集成。

### 8. [AbdelStark/nostr-mcp](https://github.com/AbdelStark/nostr-mcp)

- **描述**: Nostr MCP 服务器，允许与 Nostr 交互，发布笔记等。

- **备注**: 社区实现, 云服务 ☁️, Nostr 社交协议集成。

### 9. [adhikasp/mcp-twikit](https://github.com/adhikasp/mcp-twikit)

- **描述**: 与 Twitter 搜索和时间线交互。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Twitter 交互。

### 10. [arpitbatra123/mcp-googletasks](https://github.com/arpitbatra123/mcp-googletasks)

- **描述**: 与 Google Tasks API 交互的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Google Tasks 管理 (TS)。

### 11. [carterlasalle/mac_messages_mcp](https://github.com/carterlasalle/mac_messages_mcp)

- **描述**: 安全地与 iMessage 数据库交互的 MCP 服务器，允许 LLM 查询分析对话 (含验证/附件/联系人/群聊/收发)。

- **备注**: 社区实现, Python 开发 🏎️, 本地运行 🏠, macOS iMessage 集成 🍎。

### 12. [chaindead/telegram-mcp](https://github.com/chaindead/telegram-mcp)

- **描述**: Telegram API 集成，访问用户数据、管理对话、检索消息和处理已读状态。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, Telegram 集成 (Go)。

### 13. [ClaudePost](https://github.com/ZilongXue/claude-post)

- **描述**: 实现 Gmail 的无缝邮件管理，支持邮件搜索、阅读和发送。

- **备注**: 社区实现, Python 开发, Gmail 邮件操作。

### 14. [Discord (by v-3)](https://github.com/v-3/discordmcp)

- **描述**: 通过机器人连接 Discord 服务器，读写频道消息。

- **备注**: 社区实现, TypeScript 开发, Discord 消息交互。

### 15. [gotoolkits/wecombot](https://github.com/gotoolkits/mcp-wecombot-server.git)

- **描述**: 向企业微信群机器人发送各种类型消息的 MCP 服务器应用。

- **备注**: 社区实现, Go 开发 🚀, 云服务 ☁️, 企业微信机器人。

### 16. [Gmail](https://github.com/GongRzhe/Gmail-MCP-Server)

- **描述**: 支持自动认证的 Gmail 集成，用于 Claude Desktop。

- **备注**: 社区实现, Python 开发, Gmail 集成 (带认证)。

### 17. [Gmail Headless](https://github.com/baryhuang/mcp-headless-gmail)

- **描述**: 可远程托管的 Gmail 服务器，无需本地凭证或文件系统即可收发邮件。

- **备注**: 社区实现, Python 开发, 远程 Gmail 操作。

### 18. [Google Calendar (by v-3)](https://github.com/v-3/google-calendar)

- **描述**: 集成 Google Calendar，检查日程、查找空闲时间、添加/删除事件。

- **备注**: 社区实现, TypeScript 开发, Google 日历管理。

### 19. [hannesrudolph/imessage-query-fastmcp-mcp-server](https://github.com/hannesrudolph/imessage-query-fastmcp-mcp-server)

- **描述**: 提供对 iMessage 数据库安全访问的 MCP 服务器 (FastMCP)，LLM 可查询分析对话 (含验证/附件)。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, macOS iMessage 集成 🍎 (FastMCP)。

### 20. [jagan-shanmugam/mattermost-mcp-host](https://github.com/jagan-shanmugam/mattermost-mcp-host)

- **描述**: 提供对 Mattermost 团队、频道和消息访问的 MCP 服务器及主机。主机作为机器人集成，可配置 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Mattermost 集成。

### 21. [lharries/whatsapp-mcp](https://github.com/lharries/whatsapp-mcp)

- **描述**: 用于搜索个人 WhatsApp 消息、联系人以及向个人或群组发送消息的 MCP 服务器。

- **备注**: 社区实现, Python/Go 开发 🐍🏎️, WhatsApp 交互。

### 22. [LINE](https://github.com/amornpan/py-mcp-line)

- **描述**: 集成 LINE Bot，让 AI 读取和分析 LINE 对话。

- **备注**: 社区实现, Python 开发, LINE 对话分析。

### 23. [MarkusPfundstein/mcp-gsuite](https://github.com/MarkusPfundstein/mcp-gsuite)

- **描述**: Gmail 和 Google Calendar 集成。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Gmail/Google Calendar 集成。

### 24. [Apple Calendar](https://github.com/Omar-v2/mcp-ical)

- **描述**: 与 macOS 日历交互，创建/修改事件、列出日程、查找空闲时段等。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, macOS 日历管理 🍎。

### 25. [sawa-zen/vrchat-mcp](https://github.com/sawa-zen/vrchat-mcp)

- **描述**: 与 VRChat API 交互的 MCP 服务器。可获取好友、世界、虚拟形象等信息。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, VRChat API 交互。

### 26. [takumi0706/google-calendar-mcp](https://github.com/takumi0706/google-calendar-mcp)

- **描述**: 与 Google Calendar API 交互的 MCP 服务器 (TypeScript 版)。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Google Calendar 集成 (TS)。

### 27. [tomba-io/tomba-mcp-server](https://github.com/tomba-io/tomba-mcp-server)

- **描述**: 邮箱发现、验证和数据丰富工具。可查找邮箱地址、验证可送达性、丰富联系人数据、发现作者和 LinkedIn 档案、验证手机号码并分析技术栈。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 邮箱验证与联系人数据丰富。

### 28. [teddyzxcv/ntfy-mcp](https://github.com/teddyzxcv/ntfy-mcp)

- **描述**: 使用 ntfy 向手机发送通知的 MCP 服务器。

- **备注**: 社区实现, ntfy 通知。

### 29. [Telegram](https://github.com/chigwell/telegram-mcp)

- **描述**: 通过 Telethon 集成 Telegram，支持分页读取聊天、检索和发送消息。

- **备注**: 社区实现, Python 开发, Telegram 消息交互。

### 30. [team-telnyx/telnyx-mcp-server](https://github.com/team-telnyx/telnyx-mcp-server)

- **描述**: Telnyx 官方 MCP 服务器，用于构建 AI 驱动的通信应用。创建语音助手、发送短信、管理电话号码、集成实时消息。

- **备注**: 官方实现 (Telnyx) 🎖️, Python 开发 🐍, 云服务 ☁️, 电话/短信/AI 语音助手。

### 31. [userad/didlogic_mcp](https://github.com/UserAd/didlogic_mcp)

- **描述**: DIDLogic MCP 服务器。增加管理 SIP 端点、号码和目的地的功能。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, DIDLogic (VoIP) 集成。

### 32. [X (Twitter) (by vidhupv)](https://github.com/vidhupv/x-mcp)

- **描述**: 直接通过 Claude 创建、管理和发布 X/Twitter 推文。

- **备注**: 社区实现, Python 开发, Twitter 发推管理。

### 33. [VibeMarketing](https://vibemarketing.ninja/mcp)

- **描述**: X/Twitter 和 LinkedIn 社交媒体调度工具，支持 AI 驱动的内容生成。OAuth 身份验证，计划发布，账户管理，订阅跟踪。

- **备注**: 远程 MCP 服务器 ☁️，社交媒体营销自动化。

### 34. [Google Tasks (by zcaceres)](https://github.com/zcaceres/gtasks-mcp)

- **描述**: Google Tasks API 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Google Tasks 管理 (TS)。

---

## 💰 金融与加密货币

让 AI 能够获取金融数据、分析股票、与区块链交互等

### 1. [Adfin](https://github.com/Adfin-Engineering/mcp-server-adfin)

- **描述**: Adfin 官方集成，获得付款所需的唯一平台 - 统一支付、发票和会计对账。

- **备注**: 官方实现 (Adfin) 🎖️, 支付和会计平台。

### 2. [BICScan](https://github.com/ahnlabio/bicscan-mcp)

- **描述**: 获取 EVM 区块链地址（EOA, CA, ENS）甚至域名的风险评分/资产持有情况。 (BICScan 官方)

- **备注**: 官方实现 (AhnLab) 🎖️, Python 开发 🐍, 云服务 ☁️, 区块链地址风险分析。

### 3. [Bankless Onchain](https://github.com/bankless/onchain-mcp)

- **描述**: 查询链上数据，如 ERC20 代币、交易历史、智能合约状态。 (Bankless 官方)

- **备注**: 官方实现 (Bankless) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 链上数据查询。

### 4. [base/base-mcp](https://github.com/base/base-mcp)

- **描述**: Base Network 集成，提供链上工具，允许与 Base 网络和 Coinbase API 交互 (钱包/转账/合约/DeFi)。

- **备注**: 官方实现 (Base/Coinbase) 🎖️, TypeScript 开发 📇, 云服务 ☁️, Base 链与 Coinbase API。

### 5. [Chargebee](https://github.com/chargebee/agentkit/tree/main/modelcontextprotocol)

- **描述**: Chargebee 官方集成，将 AI 代理连接到 Chargebee 计费平台。

- **备注**: 官方实现 (Chargebee) 🎖️, TypeScript 开发 📇, 云服务 ☁️, Chargebee 计费管理。

### 6. [codex-data/codex-mcp](https://github.com/Codex-Data/codex-mcp)

- **描述**: Codex API 集成，提供 60+ 网络上实时丰富的区块链和市场数据。

- **备注**: 官方实现 (Codex Data) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 多链实时数据。

### 7. [coinpaprika/dexpaprika-mcp](https://github.com/coinpaprika/dexpaprika-mcp)

- **描述**: Coinpaprika 的 DexPaprika MCP 服务器，暴露高性能 DexPaprika API (20+ 链/5M+ 代币/实时价格/流动性/历史数据)。

- **备注**: 官方实现 (Coinpaprika) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 跨平台 🍎🪟🐧, DEX 聚合数据。

### 8. [Financial Datasets](https://github.com/financial-datasets/mcp-server)

- **描述**: 专为 AI 代理设计的股票市场 API。

- **备注**: 官方实现, Python 开发, AI 友好型股票数据。

### 9. [heurist-network/heurist-mesh-mcp-server](https://github.com/heurist-network/heurist-mesh-mcp-server)

- **描述**: 访问 Heurist Mesh 网络中的专业 Web3 AI 代理 (区块链分析/合约安全/代币度量等)。 (Heurist 官方)

- **备注**: 官方实现 (Heurist) 🎖️, Python 开发 🐍, 云端/本地 🏠☁️, Web3 AI 代理网络。

### 10. [Stripe](https://github.com/stripe/agent-toolkit)

- **描述**: Stripe 官方集成，与 Stripe API 交互，处理支付、客户和退款。

- **备注**: 官方实现 (Stripe), TypeScript 开发, Stripe 支付处理。

### 11. [Thirdweb](https://github.com/thirdweb-dev/ai/tree/main/python/thirdweb-mcp)

- **描述**: Thirdweb 官方集成，读写 2000+ 区块链，查询数据、分析/部署合约、执行交易。

- **备注**: 官方实现 (Thirdweb), Python 开发, 多链区块链交互。

### 12. [ajtgjmdjp/edinet-mcp](https://github.com/ajtgjmdjp/edinet-mcp)

- **描述**: EDINET API 集成，解析日本企业 XBRL 财务报告，提供 161 个标签、26 个财务指标和多公司筛选功能。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 日本 EDINET 财务数据。

### 13. [ajtgjmdjp/estat-mcp](https://github.com/ajtgjmdjp/estat-mcp)

- **描述**: 日本政府统计门户 [e-Stat](https://www.e-stat.go.jp/) 的 MCP 服务器。搜索和获取人口、GDP、CPI、劳动、贸易等 3,000+ 统计表。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 本地运行 🏠, 日本政府统计数据。

### 14. [ajtgjmdjp/boj-mcp](https://github.com/ajtgjmdjp/boj-mcp)

- **描述**: 日本银行统计数据 MCP 服务器。访问 CGPI、短观调查、资金循环、国际收支等 16 个数据集。无需 API 密钥。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 日银统计数据。

### 15. [anjor/coinmarket-mcp-server](https://github.com/anjor/coinmarket-mcp-server)

- **描述**: Coinmarket API 集成，获取加密货币列表和报价。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, CoinMarketCap 数据。

### 16. [berlinbra/alpha-vantage-mcp](https://github.com/berlinbra/alpha-vantage-mcp)

- **描述**: Alpha Vantage API 集成，获取股票和加密货币信息。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, AlphaVantage 金融数据 (另一版本)。

### 17. [bitteprotocol/mcp](https://github.com/BitteProtocol/mcp)

- **描述**: Bitte Protocol 集成，在多个区块链上运行 AI Agents。

- **备注**: 社区实现, TypeScript 开发 📇, Bitte Protocol 区块链 Agent。

### 18. [Bsc-mcp](https://github.com/TermiX-official/bsc-mcp)

- **描述**: 连接 AI 与 BNB Chain，执行复杂的链上操作（转账、交易、安全检查等）。

- **备注**: 社区实现, Python 开发, BNB Chain 操作。

### 19. [EVM MCP Server](https://github.com/mcpdotdirect/evm-mcp-server)

- **描述**: 为 30+ EVM 网络提供全面的区块链服务，支持代币、NFT、智能合约、交易和 ENS。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, EVM 多链服务。

### 20. [ferdousbhai/investor-agent](https://github.com/ferdousbhai/investor-agent)

- **描述**: Yahoo Finance 集成，获取股市数据，包括期权推荐。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Yahoo Finance 数据与期权。

### 21. [ferdousbhai/tasty-agent](https://github.com/ferdousbhai/tasty-agent)

- **描述**: Tastyworks API 集成，处理 Tastytrade 上的交易活动。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Tastytrade 交易。

### 22. [getalby/nwc-mcp-server](https://github.com/getalby/nwc-mcp-server)

- **描述**: 由 Nostr Wallet Connect 驱动的比特币闪电网络钱包集成。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 比特币闪电网络钱包 (NWC)。

### 23. [intentos-labs/beeper-mcp](https://github.com/intentos-labs/beeper-mcp)

- **描述**: Beeper 在 BSC 上提供交易，包括余额/代币转移、Pancakeswap 代币交换和 beeper 奖励领取。

- **备注**: 社区实现, Python 开发 🐍, BSC 链交互 (Beeper)。

### 24. [janswist/mcp-dexscreener](https://github.com/janswist/mcp-dexscreener)

- **描述**: 使用开放免费的 Dexscreener API 获取实时链上市场价格。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Dexscreener 实时价格。

### 25. [kukapay/crypto-feargreed-mcp](https://github.com/kukapay/crypto-feargreed-mcp)

- **描述**: 提供实时和历史的加密货币恐惧与贪婪指数数据。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 加密货币情绪指数。

### 26. [kukapay/crypto-indicators-mcp](https://github.com/kukapay/crypto-indicators-mcp)

- **描述**: 提供一系列加密货币技术分析指标和策略的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 加密货币技术指标。

### 27. [kukapay/crypto-portfolio-mcp](https://github.com/kukapay/crypto-portfolio-mcp)

- **描述**: 用于跟踪和管理加密货币投资组合分配的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 加密货币投资组合管理。

### 28. [kukapay/crypto-sentiment-mcp](https://github.com/kukapay/crypto-sentiment-mcp)

- **描述**: 向 AI 代理提供加密货币情绪分析的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 加密货币情绪分析。

### 29. [kukapay/cryptopanic-mcp-server](https://github.com/kukapay/cryptopanic-mcp-server)

- **描述**: 向 AI 代理提供最新加密货币新闻 (由 CryptoPanic 驱动)。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, CryptoPanic 新闻。

### 30. [kukapay/dune-analytics-mcp](https://github.com/kukapay/dune-analytics-mcp)

- **描述**: 将 Dune Analytics 数据桥接到 AI 代理的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Dune Analytics 集成。

### 31. [kukapay/freqtrade-mcp](https://github.com/kukapay/freqtrade-mcp)

- **描述**: 与 Freqtrade 加密货币交易机器人集成的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Freqtrade 交易机器人集成。

### 32. [kukapay/jupiter-mcp](https://github.com/kukapay/jupiter-mcp)

- **描述**: 使用 Jupiter 的新 Ultra API 在 Solana 区块链上执行代币交换的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Solana Jupiter 交易 (Ultra API)。

### 33. [kukapay/pancakeswap-poolspy-mcp](https://github.com/kukapay/pancakeswap-poolspy-mcp)

- **描述**: 跟踪 Pancake Swap 上新创建池子的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, PancakeSwap 新池子监控。

### 34. [kukapay/rug-check-mcp](https://github.com/kukapay/rug-check-mcp)

- **描述**: 检测 Solana meme 代币潜在风险的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Solana Meme 币风险检测。

### 35. [kukapay/thegraph-mcp](https://github.com/kukapay/thegraph-mcp)

- **描述**: 用来自 The Graph 的索引化区块链数据赋能 AI 代理的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, The Graph 数据集成。

### 36. [kukapay/token-minter-mcp](https://github.com/kukapay/token-minter-mcp)

- **描述**: 为 AI 代理提供在多个区块链上铸造 ERC-20 代币工具的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 多链 ERC-20 铸造。

### 37. [kukapay/token-revoke-mcp](https://github.com/kukapay/token-revoke-mcp)

- **描述**: 用于检查和撤销多个区块链上 ERC-20 代币授权的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 多链 ERC-20 授权管理。

### 38. [kukapay/uniswap-poolspy-mcp](https://github.com/kukapay/uniswap-poolspy-mcp)

- **描述**: 跟踪多个区块链上 Uniswap 新创建流动性池的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Uniswap 新池子监控 (多链)。

### 39. [kukapay/uniswap-trader-mcp](https://github.com/kukapay/uniswap-trader-mcp)

- **描述**: 用于 AI 代理在多个区块链上自动化 Uniswap DEX 代币交换的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Uniswap 自动交易 (多链)。

### 40. [kukapay/whale-tracker-mcp](https://github.com/kukapay/whale-tracker-mcp)

- **描述**: 用于跟踪加密货币巨鲸交易的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 加密货币巨鲸追踪。

### 41. [laukikk/alpaca-mcp](https://github.com/laukikk/alpaca-mcp)

- **描述**: Alpaca 交易 API 的 MCP 服务器，用于管理股票和加密货币投资组合、下单和访问市场数据。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Alpaca 交易 API 集成。

### 42. [longportapp/openapi](https://github.com/longportapp/openapi/tree/main/mcp)

- **描述**: LongPort OpenAPI 提供实时股市数据，通过 MCP 为 AI 提供分析和交易能力。

- **备注**: 官方实现 (LongPort) 🎖️, Python 开发 🐍, 云服务 ☁️, LongPort 股票数据与交易。

### 43. [mcpdotdirect/starknet-mcp-server](https://github.com/mcpdotdirect/starknet-mcp-server)

- **描述**: 全面的 Starknet 区块链集成，支持原生代币 (ETH, STRK)、智能合约、StarknetID 解析和代币转移。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Starknet 全功能集成。

### 44. [minhyeoky/mcp-server-ledger](https://github.com/minhyeoky/mcp-server-ledger)

- **描述**: ledger-cli 集成，用于管理金融交易和生成报告。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, ledger-cli 记账。

### 45. [narumiruna/yfinance-mcp](https://github.com/narumiruna/yfinance-mcp)

- **描述**: 使用 Yahoo Finance API 获取金融数据，方便进行股票分析。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Yahoo Finance 数据获取。

### 46. [openMF/mcp-mifosx](https://github.com/openMF/mcp-mifosx)

- **描述**: 核心银行集成，用于管理客户、贷款、储蓄、股份、金融交易和生成财务报告。

- **备注**: 社区实现 (OpenMF), 云端/本地 ☁️🏠, Mifos X 核心银行系统集成。

### 47. [pwh-pwh/coin-mcp-server](https://github.com/pwh-pwh/coin-mcp-server)

- **描述**: Bitget API 获取加密货币价格。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Bitget 价格获取。

### 48. [QuantGeekDev/coincap-mcp](https://github.com/QuantGeekDev/coincap-mcp)

- **描述**: 使用 CoinCap 公共 API 的实时加密货币市场数据集成，无需 API Key 即可访问价格和市场信息。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, CoinCap 实时数据。

### 49. [SaintDoresh/Crypto-Trader-MCP-ClaudeDesktop](https://github.com/SaintDoresh/Crypto-Trader-MCP-ClaudeDesktop.git)

- **描述**: 使用 CoinGecko API 提供加密货币市场数据的 MCP 工具。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, CoinGecko 数据。

### 50. [SaintDoresh/YFinance-Trader-MCP-ClaudeDesktop](https://github.com/SaintDoresh/YFinance-Trader-MCP-ClaudeDesktop.git)

- **描述**: 使用 Yahoo Finance API 提供股市数据和分析的 MCP 工具。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Yahoo Finance 数据分析。

### 51. [Solana Agent Kit](https://github.com/sendaifun/solana-agent-kit/tree/main/examples/agent-kit-mcp-server)

- **描述**: 使用 Solana Agent Kit 与 Solana 区块链交互，支持 40+ 协议操作。

- **备注**: 社区实现, TypeScript 开发, Solana 链交互。

### 52. [AlphaVantage](https://github.com/calvernaz/alphavantage)

- **描述**: AlphaVantage 股票市场数据 API 服务器。

- **备注**: 社区实现, Python 开发, AlphaVantage 金融数据。

### 53. [xpaysh/awesome-x402](https://github.com/xpaysh/awesome-x402)

- **描述**: x402 支付协议资源目录，包含 MCP 服务器、SDK 和工具，用于基于 HTTP 402 的 USDC 支付（支持 Base、Arbitrum 等 EVM 链）。

- **备注**: 社区实现, 云服务 ☁️, x402 协议生态资源汇总。

---

## 📁 文件系统与存储

让 AI 能够访问本地文件、操作云存储等

### 1. [Box](https://github.com/box-community/mcp-server-box)

- **描述**: Box 官方集成，通过 Box AI 与智能内容管理平台交互。

- **备注**: 官方实现 (Box Community) 🎖️, Python 开发, Box 云存储交互。

### 2. [Fireproof](https://github.com/fireproof-storage/mcp-database-server)

- **描述**: Fireproof 官方集成，不可变账本数据库，支持实时同步。 (也含数据库功能)

- **备注**: 官方实现 (Fireproof) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 分布式数据库/存储同步。

### 3. [microsoft/markitdown](https://github.com/microsoft/markitdown/tree/main/packages/markitdown-mcp)

- **描述**: MarkItDown MCP 工具访问 - 一个将多种文件格式（本地或远程）转换为 Markdown 以供 LLM 使用的库。

- **备注**: 官方实现 (Microsoft) 🎖️, Python 开发 🐍, 本地运行 🏠, 文件转 Markdown。

### 4. [Xuanwo/mcp-server-opendal](https://github.com/Xuanwo/mcp-server-opendal)

- **描述**: 使用 Apache OpenDAL™ 访问任何存储。

- **备注**: 社区实现, Python 开发 🐍, 本地/云端 🏠☁️, Apache OpenDAL 通用存储访问。

### 5. [modelcontextprotocol/server-filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)

- **描述**: 官方参考实现，提供对本地文件系统的直接访问，带可配置权限。

- **备注**: 官方参考, TypeScript 开发 📇, 本地运行 🏠, 本地文件系统操作。

### 6. [modelcontextprotocol/server-google-drive](https://github.com/modelcontextprotocol/servers/tree/main/src/gdrive)

- **描述**: 官方参考实现，集成 Google Drive，用于列出、读取和搜索文件。

- **备注**: 官方参考, TypeScript 开发 📇, 云服务 ☁️, Google Drive 文件管理。

### 7. [calclavia/mcp-obsidian](https://github.com/calclavia/mcp-obsidian)

- **描述**: 读取和搜索 Obsidian 库或任何包含 Markdown 笔记的目录。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Obsidian/Markdown 文件访问。

### 8. [cyberchitta/llm-context.py](https://github.com/cyberchitta/llm-context.py)

- **描述**: 通过 MCP 或剪贴板与 LLM 共享代码上下文。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 代码上下文共享。

### 9. [exoticknight/mcp-file-merger](https://github.com/exoticknight/mcp-file-merger)

- **描述**: 文件合并工具，适用于 AI 聊天长度限制。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, 文件合并。

### 10. [filesystem@quarkiverse/quarkus-mcp-servers](https://github.com/quarkiverse/quarkus-mcp-servers/tree/main/filesystem)

- **描述**: 使用 Quarkus 在 Java 中实现的允许浏览和编辑文件系统。可用作 jar 或原生镜像。

- **备注**: 社区实现 (Quarkiverse), Java 开发 ☕, 本地运行 🏠, Java 文件系统操作。

### 11. [Golang Filesystem Server](https://github.com/mark3labs/mcp-filesystem-server)

- **描述**: Go 语言实现的安全文件操作，带可配置访问控制。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, 本地文件系统操作 (Go)。

### 12. [hmk/box-mcp-server](https://github.com/hmk/box-mcp-server)

- **描述**: Box 集成，用于列出、读取和搜索文件 (社区实现版本)。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Box 文件操作 (社区 TS 版)。

### 13. [mamertofabian/mcp-everything-search](https://github.com/mamertofabian/mcp-everything-search)

- **描述**: 在 Windows 上使用 Everything SDK 快速搜索文件。 (Awesome列表更通用)

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Windows 快速文件搜索 🪟。

### 14. [Everything Search (mamertofabian)](https://github.com/mamertofabian/mcp-everything-search)

- **描述**: [更新] 在 Windows/macOS/Linux 上快速搜索文件（使用 Everything/mdfind/locate）。 (更新自Awesome列表描述)

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 跨平台 🪟🍎🐧 快速文件搜索。

---

## 📊 数据分析、处理与可视化

让 AI 能够处理表格数据、生成图表、进行数据探索等

### 1. [Axiom](https://github.com/axiomhq/mcp-server-axiom)

- **描述**: Axiom 官方集成，用自然语言查询和分析 Axiom 日志、追踪等事件数据。

- **备注**: 官方实现 (Axiom), Python 开发, Axiom 日志分析。

### 2. [Comet Opik](https://github.com/comet-ml/opik-mcp)

- **描述**: Comet 官方集成，用自然语言查询和分析 Opik 日志、追踪、提示等 LLM 遥测数据。

- **备注**: 官方实现 (Comet ML) 🎖️, TypeScript 开发 📇, 云端/本地 🏠☁️, LLM 可观测性数据分析。

### 3. [flowcore/mcp-flowcore-platform](https://github.com/flowcore-io/mcp-flowcore-platform)

- **描述**: 与 Flowcore 交互以执行操作、摄取数据，并分析、交叉引用和利用数据核心中的任何数据。

- **备注**: 官方实现 (Flowcore) 🎖️, TypeScript 开发 📇, 云端/本地 🏠☁️, Flowcore 数据平台交互。

### 4. [GreptimeDB](https://github.com/GreptimeTeam/greptimedb-mcp-server)

- **描述**: GreptimeDB 官方集成，让 AI 安全地探索和分析 GreptimeDB 中的时序数据。(已在数据库部分列出)

- **备注**: 官方实现 (Greptime) 🎖️, Python 开发 🐍, 本地运行 🏠, GreptimeDB 时序数据分析。

### 5. [JordiNei/mcp-databricks-server](https://github.com/JordiNeil/mcp-databricks-server)

- **描述**: 连接到 Databricks API，允许 LLM 运行 SQL 查询、列出作业和获取作业状态。

- **备注**: 社区实现, Databricks API 集成。

### 6. [jwaxman19/qlik-mcp](https://github.com/jwaxman19/qlik-mcp)

- **描述**: Qlik Cloud API 的 MCP 服务器，支持查询应用、工作表和从可视化中提取数据 (带认证和速率限制)。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Qlik Cloud API 集成。

### 7. [Keboola](https://github.com/keboola/keboola-mcp-server)

- **描述**: Keboola 官方集成，在单一平台上构建数据工作流、集成和分析。

- **备注**: 官方实现 (Keboola) 🎖️, Python 开发, Keboola 数据平台。

### 8. [yzfly/mcp-excel-server](https://github.com/yzfly/mcp-excel-server)

- **描述**: 通过自然语言与 Excel 交互的 MCP 服务器。

- **备注**: 社区标杆, Excel 读写、分析、可视化。

### 9. [ChronulusAI/chronulus-mcp](https://github.com/ChronulusAI/chronulus-mcp)

- **描述**: 使用 Chronulus AI 预测和预测代理预测任何事物。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, AI 预测服务。

### 10. [Excel (by haris-musa)](https://github.com/haris-musa/excel-mcp-server)

- **描述**: Excel 操作，包括读写、工作表管理、格式化、图表和数据透视表 (提供更高级的功能)。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Excel 高级操作。

### 11. [Data Exploration](https://github.com/reading-plus-ai/mcp-server-data-exploration)

- **描述**: 对 .csv 数据集进行自主数据探索，轻松获得智能见解（**注意：会执行代码**）。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, CSV 数据自动探索。

### 12. [Dataset Viewer](https://github.com/privetin/dataset-viewer)

- **描述**: 浏览和分析 Hugging Face 数据集，支持搜索、过滤、统计和导出。

- **备注**: 社区实现, Python 开发, HuggingFace 数据集浏览。

### 13. [data-check](https://github.com/liuxiaotong/data-check)

- **描述**: 数据质检工具 — 自动化质量检查、异常检测、分布分析，保障数据集质量。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 数据质检与异常检测。

### 14. [Vega-Lite](https://github.com/isaacwasserman/mcp-vegalite-server)

- **描述**: 使用 Vega-Lite 格式和渲染器从获取的数据生成可视化图表。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 数据可视化生成。

### 15. [QuickChart](https://github.com/GongRzhe/Quickchart-MCP-Server)

- **描述**: 使用 QuickChart.io 生成图表。

- **备注**: 社区实现, Python 开发, 图表生成服务。

### 16. [Mindmap](https://github.com/YuChenSSR/mindmap-mcp-server)

- **描述**: 从包含 Markdown 代码的输入生成美观的交互式思维导图。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 思维导图生成。

### 17. [JSON](https://github.com/GongRzhe/JSON-MCP-Server)

- **描述**: JSON 处理服务器，支持 JSONPath 查询和多种操作。

- **备注**: 社区实现, Python 开发, 高级 JSON 处理。

### 18. [zcaceres/markdownify-mcp](https://github.com/zcaceres/markdownify-mcp)

- **描述**: 将几乎任何文件或 Web 内容转换为 Markdown 的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 文件/网页转 Markdown。

---

## 🛠️ 效率工具与集成 (Office, Project Management, Notes, etc.)

让 AI 能够使用日历、任务管理、项目管理、笔记等工具

### 1. [ActionKit by Paragon](https://github.com/useparagon/paragon-mcp)

- **描述**: Paragon 官方集成，通过 ActionKit API 连接 130+ SaaS 集成 (Slack, Salesforce, Gmail)。

- **备注**: 官方实现 (Paragon) 🎖️, TypeScript 开发 📇, 大规模 SaaS 集成平台。

### 2. [Dart](https://github.com/its-dart/dart-mcp-server)

- **描述**: Dart 官方集成，与 AI 原生项目管理工具 Dart 中的任务、文档、项目数据交互。

- **备注**: 官方实现 (Dart) 🎖️, TypeScript 开发 📇, Dart 项目管理。

### 3. [Fibery](https://github.com/Fibery-inc/fibery-mcp-server)

- **描述**: Fibery 官方集成，在 Fibery 工作区中执行查询和实体操作。

- **备注**: 官方实现 (Fibery) 🎖️, TypeScript 开发 📇, Fibery 工作管理。

### 4. [Make](https://github.com/integromat/make-mcp-server)

- **描述**: Make 官方集成，将 Make 场景转换为 AI 助手可调用的工具。

- **备注**: 官方实现 (Make/Integromat) 🎖️, TypeScript 开发 📇, 本地运行 🏠, 连接 Make 生态。

### 5. [Taskade MCP](https://github.com/taskade/mcp)

- **描述**: Taskade 官方 MCP 集成，连接任务、项目、自动化流程和 AI Agent，实现团队协作与工作流自动化。

- **备注**: 官方实现 (Taskade) 🎖️, Node.js 开发, 云服务 ☁️, 项目管理与协作。

### 6. [PipedreamHQ/pipedream](https://github.com/PipedreamHQ/pipedream/tree/master/modelcontextprotocol)

- **描述**: Pipedream 官方集成，一站式连接 2500+ API，集成 8000+ 工具，并管理用户服务器。

- **备注**: 官方实现 (Pipedream) 🎖️, Node.js 开发, 云端/本地 ☁️🏠, 超强 API/工具集成平台。

### 7. [Rember](https://github.com/rember/rember-mcp)

- **描述**: 在 Rember 中创建间隔重复抽认卡，记住聊天中学到的任何东西。 (Rember 官方)

- **备注**: 官方实现 (Rember) 🎖️, TypeScript 开发 📇, 本地运行 🏠, 间隔重复记忆工具。

### 8. [Zapier](https://zapier.com/mcp)

- **描述**: Zapier 官方集成，将 AI 代理即时连接到 8000+ 应用。

- **备注**: 官方实现 (Zapier), 连接 Zapier 生态。

### 9. [Airtable (by domdomegg)](https://github.com/domdomegg/airtable-mcp-server)

- **描述**: 读写 Airtable 数据库，带模式检查。(已在数据库部分列出)

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Airtable 读写。

### 10. [akseyh/bear-mcp-server](https://github.com/akseyh/bear-mcp-server)

- **描述**: 允许 AI 读取你的 Bear 笔记 (仅 macOS)。

- **备注**: 社区实现, macOS Bear 笔记读取 🍎.

### 11. [awwaiid/mcp-server-taskwarrior](https://github.com/awwaiid/mcp-server-taskwarrior)

- **描述**: 用于基本本地 taskwarrior 使用的 MCP 服务器 (添加/更新/删除任务)。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Taskwarrior 任务管理。

### 12. [Badhansen/notion-mcp](https://github.com/Badhansen/notion-mcp)

- **描述**: 与 Notion API 集成以高效管理个人待办事项列表的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Notion ToDo 管理 (Python)。

### 13. [bart6114/my-bear-mcp-server](https://github.com/bart6114/my-bear-mcp-server/)

- **描述**: 允许通过直接与 Bear 的 SQLite 数据库集成来读取 Bear 笔记应用的笔记和标签。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, macOS Bear 笔记读取 🍎 (SQLite 直连)。

### 14. [danhilse/notion_mcp](https://github.com/danhilse/notion_mcp)

- **描述**: 与 Notion API 集成以管理个人待办事项列表。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Notion ToDo 管理 (Python, 另一版本)。

### 15. [evalstate/mcp-miro](https://github.com/evalstate/mcp-miro)

- **描述**: 访问 MIRO 白板，批量创建和读取项目。需要 REST API 的 OAUTH 密钥。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Miro 白板交互。

### 16. [fradser/mcp-server-apple-reminders](https://github.com/FradSer/mcp-server-apple-reminders)

- **描述**: 用于与 macOS 上的 Apple Reminders 交互的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, macOS Reminders 管理 🍎。

### 17. [hiromitsusasaki/raindrop-io-mcp-server](https://github.com/hiromitsusasaki/raindrop-io-mcp-server)

- **描述**: 允许 LLM 使用 MCP 与 Raindrop.io 书签交互的集成。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Raindrop.io 书签管理。

### 18. [hmk/attio-mcp-server](https://github.com/hmk/attio-mcp-server)

- **描述**: 允许 AI 客户端在 Attio CRM 中管理记录和笔记。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Attio CRM 管理。

### 19. [ivo-toby/contentful-mcp](https://github.com/ivo-toby/contentful-mcp)

- **描述**: 在 Contentful Space 中更新、创建、删除内容、内容模型和资产。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Contentful CMS 管理。

### 20. [kelvin6365/plane-mcp-server](https://github.com/kelvin6365/plane-mcp-server)

- **描述**: 此 MCP 服务器将帮助您通过 Plane 的 API 管理项目和问题。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, Plane 项目管理。

### 21. [k-jarzyna/mcp-miro](https://github.com/k-jarzyna/mcp-miro)

- **描述**: Miro MCP 服务器，暴露官方 Miro SDK 中可用的所有功能。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Miro 白板交互 (更全面)。

### 22. [kj455/mcp-kibela](https://github.com/kj455/mcp-kibela)

- **描述**: 允许 AI 模型与 Kibela 交互。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Kibela 知识库交互。

### 23. [KS-GEN-AI/confluence-mcp-server](https://github.com/KS-GEN-AI/confluence-mcp-server)

- **描述**: 通过 CQL 获取 Confluence 数据并阅读页面。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 跨平台 🍎🪟, Confluence 数据读取。

### 24. [KS-GEN-AI/jira-mcp-server](https://github.com/KS-GEN-AI/jira-mcp-server)

- **描述**: 通过 JQL 和 API 读取 Jira 数据，并执行请求以创建和编辑工单。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 跨平台 🍎🪟, Jira 数据读写。

### 25. [lciesielski/mcp-salesforce](https://github.com/lciesielski/mcp-salesforce-example)

- **描述**: 具有与 Salesforce 实例交互基本演示的 MCP 服务器。

- **备注**: 社区实现, 本地/云端 🏠☁️, Salesforce 集成示例。

### 26. [Linear (by jerhadf)](https://github.com/jerhadf/linear-mcp-server)

- **描述**: 与 Linear API 交互进行项目管理，包括搜索、创建和更新 Issues。

- **备注**: 社区实现, TypeScript 开发, Linear 项目管理。

### 27. [MarkusPfundstein/mcp-obsidian](https://github.com/MarkusPfundstein/mcp-obsidian)

- **描述**: 通过 REST API 与 Obsidian 交互。

- **备注**: 社区实现, Python 开发 🐍, 云端/本地 🏠☁️, Obsidian REST API 交互。

### 28. [Notion (by v-3)](https://github.com/v-3/notion-server)

- **描述**: Notion 集成，通过 Claude 搜索、读取、更新和创建页面。

- **备注**: 社区实现, TypeScript 开发 📇, Notion 页面管理。

### 29. [recursechat/mcp-server-apple-shortcuts](https://github.com/recursechat/mcp-server-apple-shortcuts)

- **描述**: 与 Apple Shortcuts 集成的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, macOS Apple Shortcuts 集成 🍎。

### 30. [roychri/mcp-server-asana](https://github.com/roychri/mcp-server-asana)

- **描述**: Asana 的 MCP 服务器实现，允许从 MCP 客户端与 Asana API 对话。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Asana 项目管理。

### 31. [sirmews/apple-notes-mcp](https://github.com/sirmews/apple-notes-mcp)

- **描述**: 允许 AI 从本地 Apple Notes 数据库读取 (仅 macOS)。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, macOS Apple Notes 读取 🍎。

### 32. [sooperset/mcp-atlassian](https://github.com/sooperset/mcp-atlassian)

- **描述**: Atlassian 产品 (Confluence 和 Jira) 的 MCP 服务器。支持 Cloud/Server/DC。提供全面的工具用于搜索、读取、创建和管理内容。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Confluence/Jira 全功能管理。

### 33. [suekou/mcp-notion-server](https://github.com/suekou/mcp-notion-server)

- **描述**: 与 Notion API 交互。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Notion API 交互 (另一版本)。

### 34. [tacticlaunch/mcp-linear](https://github.com/tacticlaunch/mcp-linear)

- **描述**: 与 Linear 项目管理系统集成。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 跨平台 🍎🪟🐧, Linear 项目管理 (另一版本)。

### 35. [Todoist](https://github.com/abhiz123/todoist-mcp-server)

- **描述**: 与 Todoist 交互来管理你的任务。

- **备注**: 社区实现, Python 开发, Todoist 任务管理。

### 36. [Home Assistant (by tevonsb)](https://github.com/tevonsb/homeassistant-mcp)

- **描述**: 与 Home Assistant 交互，查看和控制灯光、开关、传感器等智能家居设备。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 智能家居控制。

### 37. [allenporter/mcp-server-home-assistant](https://github.com/allenporter/mcp-server-home-assistant)

- **描述**: 通过 MCP 服务器暴露所有 Home Assistant 语音意图，实现家庭控制。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Home Assistant 语音控制。

### 38. [yuna0x0/hackmd-mcp](https://github.com/yuna0x0/hackmd-mcp)

- **描述**: 允许 AI 模型与 HackMD 交互。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, HackMD 协作笔记。

### 39. [caol64/wenyan-mcp](https://github.com/caol64/wenyan-mcp)

- **描述**: 文颜 MCP Server， 让 AI 将 Markdown 文章自动排版后发布至微信公众号。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 推荐 Docker 部署。

---

## multimedia 多媒体与内容创作

让 AI 能够生成动画、编辑视频、处理图像、语音合成等

### 1. [Amazon Bedrock Nova Canvas](https://github.com/zxkane/mcp-server-amazon-bedrock)

- **描述**: 使用 Amazon Nova Canvas 模型进行图像生成。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, AWS Bedrock 图像生成。

### 2. [apinetwork/piapi-mcp-server](https://github.com/apinetwork/piapi-mcp-server)

- **描述**: PiAPI MCP 服务器使用户能够直接从 Claude 或任何其他 MCP 兼容应用生成 Midjourney/Flux/Kling/Hunyuan/Udio/Trellis 等媒体内容。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 多模型媒体内容生成 (PiAPI)。

### 3. [abhiemj/manim-mcp-server](https://github.com/abhiemj/manim-mcp-server)

- **描述**: 用 Manim 生成动画，适合制作数学、科技类可视化内容。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 跨平台 🪟🐧, 数学/科技动画。

### 4. [awkoy/replicate-flux-mcp](https://github.com/awkoy/replicate-flux-mcp)

- **描述**: 提供通过 Replicate API 生成图像的能力。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Replicate 图像生成 (Flux)。

### 5. [burningion/video-editing-mcp](https://github.com/burningion/video-editing-mcp)

- **描述**: 视频编辑神器，支持添加、分析、搜索和生成视频剪辑。

- **备注**: 社区实现, Python 开发 🐍, 视频内容创作。

### 6. [diivi/aseprite-mcp](https://github.com/diivi/aseprite-mcp)

- **描述**: 使用 Aseprite API 创建像素艺术的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Aseprite 像素艺术。

### 7. [EverArt](https://github.com/modelcontextprotocol/servers/tree/main/src/everart)

- **描述**: 官方参考实现，使用多种模型进行 AI 图像生成。

- **备注**: 官方参考, TypeScript 开发, AI 图像生成。

### 8. [ElevenLabs](https://github.com/mamertofabian/elevenlabs-mcp-server)

- **描述**: 集成 ElevenLabs TTS API，能生成包含多种声音的完整画外音。

- **备注**: 社区实现, Python 开发, 文本转语音 TTS。

### 9. [Image Generation](https://github.com/GongRzhe/Image-Generation-MCP-Server)

- **描述**: 使用 Replicate Flux 模型提供图像生成能力。

- **备注**: 社区实现, Python 开发, AI 图像生成 (Replicate)。

### 10. [InhiblabCore/mcp-image-compression](https://github.com/InhiblabCore/mcp-image-compression)

- **描述**: 用于本地压缩各种图像格式的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 图像压缩。

### 11. [j3k0/speech.sh](https://github.com/j3k0/speech.sh/blob/main/MCP_README.md)

- **描述**: 让代理大声说出内容，并在工作完成时用简短摘要通知你。

- **备注**: 社区实现, 本地运行 🏠, 语音输出/通知。

### 12. [kimtaeyoon83/mcp-server-youtube-transcript](https://github.com/kimtaeyoon83/mcp-server-youtube-transcript)

- **描述**: 获取 YouTube 字幕和转录文本供 AI 分析。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, YouTube 字幕/转录。

### 13. [Replicate](https://github.com/deepfates/mcp-replicate)

- **描述**: 在 Replicate 上搜索、运行和管理机器学习模型，处理生成的图像。

- **备注**: 社区实现, TypeScript 开发, Replicate 模型调用。

### 14. [samuelgursky/davinci-resolve-mcp](https://github.com/samuelgursky/davinci-resolve-mcp)

- **描述**: DaVinci Resolve 的 MCP 服务器集成，提供视频编辑、调色、媒体管理和项目控制的强大工具。

- **备注**: 社区实现, Python 开发 🐍, DaVinci Resolve 视频编辑。

### 15. [YouTube](https://github.com/ZubeidHendricks/youtube-mcp-server)

- **描述**: 全面的 YouTube API 集成，用于视频管理、Shorts 创建和分析。

- **备注**: 社区实现, Python 开发, YouTube 管理与分析。

### 16. [anaisbetts/mcp-youtube](https://github.com/anaisbetts/mcp-youtube)

- **描述**: 获取 YouTube 字幕 (另一版本)。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, YouTube 字幕。

### 17. [IDEA-Research/DINO-X-MCP](https://github.com/IDEA-Research/DINO-X-MCP)

- **描述**: 让 AI 具备细粒度的图像理解能力：识别、定位、描述你看到的任何目标。

- **备注**: 官方实现（IDEA-Research）, TypeScript 开发 📇, 本地运行 🏠, 图像识别理解。

---

## 📕 社交媒体与内容创作 (小红书/RedNote)

让 AI 能够进行社媒数据采集、内容发布、自动化互动及多账号管理

### 1. [xhs-toolkit](https://github.com/aki66938/xhs-toolkit)

- **描述**: 小红书创作者 MCP 工具包，支持与 AI 客户端集成，进行内容创作和发布。

- **备注**: 社区热门 🔥, Python 开发 🐍, 创作与发布工具。

### 2. [xhs-mcp](https://github.com/jobsonlook/xhs-mcp)

- **描述**: 提供小红书 MCP 服务，包含 x-s / x-t 参数获取及 JS 逆向能力。

- **备注**: 社区实现, Python 开发 🐍, 核心算法/逆向支持。

### 3. [Redbook-Search-Comment-MCP2.0](https://github.com/chenningling/Redbook-Search-Comment-MCP2.0)

- **描述**: 基于 Playwright 开发，支持自动登录、关键词搜索、笔记获取及 AI 评论发布 (适配 Claude 桌面版)。

- **备注**: 社区实现, Python 开发 🐍, 自动化操作 (Playwright), 搜索与互动。

### 4. [self-dify](https://github.com/datawhalechina/self-dify)

- **描述**: Dify 应用搭建教程，包含“小红书读书卡片”、“甜蜜哄人”等特色 AI 助手实现指南。

- **备注**: 社区教程 📚, 知识库与 Agent 搭建, Dify 集成案例。

### 5. [xhs-mcp-server](https://github.com/aicu-icu/xhs-mcp-server)

- **描述**: 基于 Electron + Web API，一键安装运行，支持极速抓取数据（笔记/评论/用户）并进行 AI 分析导出。

- **备注**: 社区实现, TypeScript 开发 📇, Electron 封装, 数据抓取与分析。

### 6. [AiClient](https://github.com/Cooosin/AiClient)

- **描述**: 旅游行程规划 AI 智能体，连接小红书搜索、高德地图和和风天气 MCP 服务。

- **备注**: 社区实现, Java 开发 ☕, 跨应用集成, 旅游场景 Agent。

### 7. [RednoteMCP](https://github.com/JonaFly/RednoteMCP)

- **描述**: 基于 Playwright 的自动化工具，支持自动登录、搜索特定关键词、获取内容及智能评论。

- **备注**: 社区实现, Python 开发 🐍, 自动化操作, 笔记检索。

### 8. [XME (XhsMcpElectron)](https://github.com/pmhw/XME)

- **描述**: 小红书 Electron 多账号自动化工具，支持 MCP 协议。

- **备注**: 社区实现, Go 开发 🐹, 多账号管理, 自动化工具。

### 9. [RedBook-Search-Comment-MCP](https://github.com/chenningling/RedBook-Search-Comment-MCP)

- **描述**: (v1.0版本) 基于 Playwright 的搜索与评论工具，帮助用户完成基础的自动化操作。

- **备注**: 社区实现, Python 开发 🐍, 旧版本归档 (建议使用 v2.0)。

### 10. [xiaohongshu-mcp-nodejs](https://github.com/ToDieOrNot/xiaohongshu-mcp-nodejs)

- **描述**: 企业级 Node.js 重构版本，支持多账号矩阵管理、反风控、数据采集与发布。

- **备注**: 社区实现, Node.js 开发 🟢, 矩阵管理, 企业级特性。

---

## 🧠 知识、记忆与 RAG

让 AI 拥有长期记忆、能够基于特定知识库回答问题等

### 1. [Agentset](https://github.com/agentset-ai/mcp-server)

- **描述**: Agentset 官方集成，连接到 Agentset 的知识库 RAG 系统。

- **备注**: 官方实现 (Agentset) 🎖️, RAG 知识库集成。

### 2. [Graphlit](https://github.com/graphlit/graphlit-mcp-server)

- **描述**: Graphlit 官方集成，将各种来源（Slack, Gmail, 播客等）内容摄入可搜索的 Graphlit 项目。

- **备注**: 官方实现 (Graphlit) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 多源内容 RAG。

### 3. [Inkeep](https://github.com/inkeep/mcp-server-python)

- **描述**: Inkeep 官方集成，基于 Inkeep 的 RAG 搜索你的内容。

- **备注**: 官方实现 (Inkeep), Python 开发, Inkeep RAG 搜索。

### 4. [Needle](https://github.com/needle-ai/needle-mcp)

- **描述**: Needle 官方集成，提供开箱即用的生产级 RAG，用于搜索和检索自有文档。

- **备注**: 官方实现 (Needle AI), TypeScript 开发, 生产级 RAG。

### 5. [pinecone-io/assistant-mcp](https://github.com/pinecone-io/assistant-mcp)

- **描述**: 连接到你的 Pinecone Assistant，并从其知识引擎中为 Agent 提供上下文。

- **备注**: 官方实现 (Pinecone) 🎖️, Rust 开发 🦀, 云服务 ☁️, Pinecone Assistant RAG。

### 6. [modelcontextprotocol/server-memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory)

- **描述**: 官方参考实现，基于知识图谱的持久记忆系统。

- **备注**: 官方参考, TypeScript 开发 📇, 本地运行 🏠, 知识图谱记忆。

### 7. [Basic Memory](https://github.com/basicmachines-co/basic-memory)

- **描述**: 本地优先的知识管理系统，从 Markdown 文件构建语义图，实现跨对话持久记忆。

- **备注**: 社区实现, TypeScript 开发, 本地 Markdown 知识图谱记忆。

### 8. [CheMiguel23/MemoryMesh](https://github.com/CheMiguel23/MemoryMesh)

- **描述**: 增强的基于图的记忆，专注于 AI 角色扮演和故事生成。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 图记忆 (角色扮演/故事)。

### 9. [cognee-mcp](https://github.com/topoteretes/cognee/tree/main/cognee-mcp)

- **描述**: GraphRAG 记忆服务器，支持自定义摄取、数据处理和搜索。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, GraphRAG 记忆。

### 10. [entanglr/zettelkasten-mcp](https://github.com/entanglr/zettelkasten-mcp)

- **描述**: 实现 Zettelkasten 知识管理方法的 MCP 服务器，允许通过 Claude 等客户端创建、链接和搜索原子笔记。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, Zettelkasten 笔记法。

### 11. [engram-rs](https://github.com/kael-bit/engram-rs)

- **描述**: 三层记忆引擎（Buffer→Working→Core），记忆根据重要性自动晋升、衰减和合并。混合语义+关键词召回，单 Rust 二进制文件。

- **备注**: 社区实现, Rust 开发 🦀, 本地运行 🏠, 三层生命周期记忆。

### 12. [hannesrudolph/mcp-ragdocs](https://github.com/hannesrudolph/mcp-ragdocs)

- **描述**: 提供通过向量搜索检索和处理文档工具的 MCP 服务器实现，使 AI 助手能用相关文档上下文增强响应。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 文档 RAG (向量搜索)。

### 13. [kaliaboi/mcp-zotero](https://github.com/kaliaboi/mcp-zotero)

- **描述**: 让 LLM 与 Zotero Cloud 上的收藏和文献来源交互的连接器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Zotero 文献管理。

### 14. [mcp-summarizer](https://github.com/0xshellming/mcp-summarizer)

- **描述**: AI 摘要 MCP 服务器，支持多种内容类型：纯文本、网页、PDF 文档、EPUB 书籍、HTML 内容。

- **备注**: 社区实现, Go 开发 📕, 云服务 ☁️, 多格式内容摘要。

### 15. [mem0ai/mem0-mcp](https://github.com/mem0ai/mem0-mcp)

- **描述**: 管理代码偏好和模式，支持语义搜索，方便在 IDE 中存取技术文档。 (Mem0 官方) (已在开发工具列出)

- **备注**: 官方实现 (Mem0 AI) 🎖️, Python 开发 🐍, 本地运行 🏠, 程序员的记忆助手和偏好管理。

### 16. [Minima](https://github.com/dmayboroda/minima)

- **描述**: 用于本地文件 RAG 的 MCP 服务器。

- **备注**: 社区实现, Python 开发, 本地文件 RAG。

### 17. [Rememberizer AI](https://github.com/skydeckai/mcp-server-rememberizer)

- **描述**: 与 Rememberizer 数据源交互，促进增强的知识检索。

- **备注**: 社区实现, Python 开发, 知识检索。

### 18. [topoteretes/cognee](https://github.com/topoteretes/cognee/tree/dev/cognee-mcp)

- **描述**: 使用各种图和向量存储的 AI 应用和 Agents 记忆管理器，允许从 30+ 数据源摄取。 (cognee-mcp 的开发分支)

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, GraphRAG 记忆 (更通用)。

### 19. [unibaseio/membase-mcp](https://github.com/unibaseio/membase-mcp)

- **描述**: 通过 Membase 以分布式方式保存和查询你的 Agent 记忆。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 分布式 Agent 记忆。

---

## 🔒 安全与分析

让 AI 能够进行安全扫描、二进制分析、风险评估等

### 1. [BICScan](https://github.com/ahnlabio/bicscan-mcp)

- **描述**: 获取 EVM 区块链地址（EOA, CA, ENS）甚至域名的风险评分/资产持有情况。 (BICScan 官方) (已在金融部分列出)

- **备注**: 官方实现 (AhnLab) 🎖️, Python 开发 🐍, 云服务 ☁️, 区块链地址风险分析。

### 2. [Semgrep](https://github.com/semgrep/mcp)

- **描述**: Semgrep 官方集成，让 AI 代理使用 Semgrep 进行代码安全扫描。 (已在开发工具列出)

- **备注**: 官方实现 (Semgrep) 🎖️, TypeScript 开发 📇, 云服务 ☁️, 代码安全扫描。

### 3. [13bm/GhidraMCP](https://github.com/13bm/GhidraMCP)

- **描述**: 集成 Ghidra 进行二进制分析，支持函数检查、反编译、内存探索、导入/导出分析等。

- **备注**: 社区实现, Python+Java 开发 🐍☕, 本地运行 🏠, 二进制逆向工程 (Ghidra)。

### 4. [atomicchonk/roadrecon_mcp_server](https://github.com/atomicchonk/roadrecon_mcp_server)

- **描述**: 用于分析来自 Azure 租户枚举的 ROADrecon 收集结果的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, Windows 本地 🪟🏠, Azure AD 分析 (ROADrecon)。

### 5. [BurtTheCoder/mcp-dnstwist](https://github.com/BurtTheCoder/mcp-dnstwist)

- **描述**: dnstwist MCP 服务器，强大的 DNS 模糊测试工具，帮助检测域名抢注、钓鱼和企业间谍活动。

- **备注**: 社区实现, TypeScript 开发 📇, Windows/云端 🪟☁️, DNS Fuzzing (dnstwist)。

### 6. [BurtTheCoder/mcp-maigret](https://github.com/BurtTheCoder/mcp-maigret)

- **描述**: maigret MCP 服务器，强大的 OSINT 工具，从各种公共来源收集用户账户信息。提供跨社交网络搜索用户名和分析 URL 的工具。

- **备注**: 社区实现, TypeScript 开发 📇, Windows/云端 🪟☁️, OSINT (maigret)。

### 7. [BurtTheCoder/mcp-shodan](https://github.com/BurtTheCoder/mcp-shodan)

- **描述**: 用于查询 Shodan API 和 Shodan CVEDB 的 MCP 服务器。提供 IP 查找、设备搜索、DNS 查找、漏洞查询等工具。

- **备注**: 社区实现, TypeScript 开发 📇, Windows/云端 🪟☁️, Shodan API 查询。

### 8. [BurtTheCoder/mcp-virustotal](https://github.com/BurtTheCoder/mcp-virustotal)

- **描述**: 用于查询 VirusTotal API 的 MCP 服务器。提供扫描 URL、分析文件哈希和检索 IP 地址报告的工具。

- **备注**: 社区实现, TypeScript 开发 📇, Windows/云端 🪟☁️, VirusTotal API 查询。

### 9. [fosdickio/binary_ninja_mcp](https://github.com/fosdickio/binary_ninja_mcp)

- **描述**: Binary Ninja 插件、MCP 服务器和桥接器，无缝集成 Binary Ninja 与 MCP 客户端，自动化二进制分析和逆向工程。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 跨平台 🍎🪟🐧, 二进制分析 (Binary Ninja)。

### 10. [fr0gger/MCP_Security](https://github.com/fr0gger/MCP_Security)

- **描述**: 用于查询 ORKL API 的 MCP 服务器。提供获取威胁报告、分析威胁行为者和检索情报来源的工具。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 威胁情报 (ORKL API)。

### 11. [Gaffx/volatility-mcp](https://github.com/Gaffx/volatility-mcp)

- **描述**: Volatility 3.x 的 MCP 服务器，允许使用 AI 助手执行内存取证分析。通过 REST API 和 LLM 使 pslist 和 netscan 等插件易于访问。

- **备注**: 社区实现, 内存取证 (Volatility)。

### 12. [heurist-network/heurist-mesh-mcp-server](https://github.com/heurist-network/heurist-mesh-mcp-server)

- **描述**: 访问 Heurist Mesh 网络中的专业 Web3 AI 代理，进行区块链分析、智能合约安全、代币度量等。 (已在金融部分列出)

- **备注**: 官方实现 (Heurist) 🎖️, Python 开发 🐍, 云端/本地 🏠☁️, Web3 安全与分析。

### 13. [mrexodia/ida-pro-mcp](https://github.com/mrexodia/ida-pro-mcp)

- **描述**: IDA Pro 的 MCP 服务器，允许使用 AI 助手执行二进制分析。此插件实现反编译、反汇编，并允许自动生成恶意软件分析报告。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 二进制逆向工程 (IDA Pro)。

### 14. [nickpending/mcp-recon](https://github.com/nickpending/mcp-recon)

- **描述**: 由 httpx 和 asnmap 驱动的对话式侦察接口和 MCP 服务器。支持不同级别的域分析、安全头检查、证书分析和 ASN 查找。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, 网络侦察 (httpx, asnmap)。

### 15. [OpenCTI](https://github.com/Spathodea-Network/opencti-mcp)

- **描述**: 与 OpenCTI 平台交互，检索威胁情报数据（报告、指标、恶意软件等）。

- **备注**: 社区实现, Python 开发, 威胁情报获取。

### 16. [qianniuspace/mcp-security-audit](https://github.com/qianniuspace/mcp-security-audit)

- **描述**: 强大的 MCP 服务器，审计 npm 包依赖项的安全漏洞。内置远程 npm 注册表集成，用于实时安全检查。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, NPM 依赖安全审计。

### 17. [rad-security/mcp-server](https://github.com/rad-security/mcp-server)

- **描述**: RAD Security 的 MCP 服务器，为 Kubernetes 和云环境提供 AI 驱动的安全洞察。提供查询 Rad Security API 等工具。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, K8s/云安全 (RAD Security)。

### 18. [roadwy/cve-search_mcp](https://github.com/roadwy/cve-search_mcp)

- **描述**: 用于查询 CVE-Search API 的 MCP 服务器。提供全面访问 CVE-Search，浏览供应商/产品、按 ID 获取 CVE、获取最新 CVE。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, CVE 漏洞信息查询 (CVE-Search)。

### 19. [sapientpants/deepsource-mcp-server](https://github.com/sapientpants/deepsource-mcp-server)

- **描述**: 与 DeepSource 集成的 MCP 服务器，为 AI 助手提供代码质量指标、问题和质量门状态的访问。

- **备注**: 社区实现, TypeScript 开发 📇, 云端/本地 ☁️🏠, 代码质量 (DeepSource)。

### 20. [sapientpants/sonarqube-mcp-server](https://github.com/sapientpants/sonarqube-mcp-server)

- **描述**: 与 SonarQube 集成的 MCP 服务器，为 AI 助手提供代码质量指标、问题和质量门状态的访问。

- **备注**: 社区实现, Rust 开发 🦀, 云端/本地 ☁️🏠, 代码质量 (SonarQube)。

### 21. [securityfortech/secops-mcp](https://github.com/securityfortech/secops-mcp)

- **描述**: 将流行的开源工具整合到单一 MCP 接口中的一体化安全测试工具箱。连接 AI 代理，实现渗透测试、漏洞赏金、威胁狩猎等任务。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 安全测试工具箱。

### 22. [model-audit](https://github.com/liuxiaotong/model-audit)

- **描述**: LLM 蒸馏检测与模型指纹审计 — 文本溯源、身份验证、蒸馏关系判定，守护模型知识产权。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, LLM 模型审计与蒸馏检测。

### 23. [Whois MCP](https://github.com/bharathvaj-ganesan/whois-mcp)

- **描述**: 对域名、IP、ASN 和 TLD 执行 whois 查询。

- **备注**: 社区实现, Python 开发, Whois 查询。

---

## 🌍 地理位置与出行

让 AI 能够处理地理位置数据、地图、天气、交通出行信息等

### 1. [Airbnb MCP Server](https://github.com/openbnb-org/mcp-server-airbnb)

- **描述**: 提供搜索 Airbnb 和获取房源详情的工具。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Airbnb 搜索。

### 2. [briandconnelly/mcp-server-ipinfo](https://github.com/briandconnelly/mcp-server-ipinfo)

- **描述**: 使用 IPInfo API 获取 IP 地址地理位置和网络信息。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, IP 地址信息 (IPInfo)。

### 3. [jagan-shanmugam/open-streetmap-mcp](https://github.com/jagan-shanmugam/open-streetmap-mcp)

- **描述**: 具有基于位置服务和地理空间数据的 OpenStreetMap MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, OpenStreetMap 数据。

### 4. [kukapay/nearby-search-mcp](https://github.com/kukapay/nearby-search-mcp)

- **描述**: 用于附近地点搜索的 MCP 服务器，带基于 IP 的位置检测。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 附近地点搜索。

### 5. [KyrieTangSheng/mcp-server-nationalparks](https://github.com/KyrieTangSheng/mcp-server-nationalparks)

- **描述**: 国家公园服务 API 集成，提供美国国家公园的公园详情、警报、游客中心、露营地和活动的最新信息。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 美国国家公园信息。

### 6. [louiscklaw/hko-mcp](https://github.com/louiscklaw/hko-mcp)

- **描述**: 从香港天文台获取天气信息的基本演示 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 香港天气。

### 7. [modelcontextprotocol/server-google-maps](https://github.com/modelcontextprotocol/servers/tree/main/src/google-maps)

- **描述**: Google Maps 集成，提供定位服务、路线规划和地点详情。

- **备注**: 官方参考, TypeScript 开发 📇, 云服务 ☁️, Google Maps 集成。

### 8. [NS Travel Information MCP Server](https://github.com/r-huijts/ns-mcp-server)

- **描述**: 访问荷兰铁路 (NS) 的旅行信息、时刻表和实时更新。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 荷兰铁路信息。

### 9. [pab1it0/tripadvisor-mcp](https://github.com/pab1it0/tripadvisor-mcp)

- **描述**: 使 LLM 能与 Tripadvisor API 交互的 MCP 服务器，支持位置数据、评论和照片。

- **备注**: 社区实现, TypeScript/Python 开发 📇🐍, Tripadvisor API 集成。

### 10. [QGIS MCP](https://github.com/jjsantos01/qgis_mcp)

- **描述**: 通过 MCP 将 QGIS Desktop 连接到 Claude AI。实现提示辅助的项目创建、图层加载、代码执行等。

- **备注**: 社区实现, QGIS 集成。

### 11. [SaintDoresh/Weather-MCP-ClaudeDesktop](https://github.com/SaintDoresh/Weather-MCP-ClaudeDesktop.git)

- **描述**: 使用 OpenWeatherMap API 提供实时天气数据、预报和历史天气信息的 MCP 工具。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, OpenWeatherMap 天气数据。

### 12. [SecretiveShell/MCP-timeserver](https://github.com/SecretiveShell/MCP-timeserver)

- **描述**: 访问任何时区的本地时间和获取当前本地时间。 (已在“其他”部分列出Time)

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 时间/时区工具。

### 13. [webcoderz/MCP-Geo](https://github.com/webcoderz/MCP-Geo)

- **描述**: 用于 nominatim, ArcGIS, Bing 的地理编码 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 地理编码服务。

### 14. [ip2location/mcp-ip2location-io](https://github.com/ip2location/mcp-ip2location-io)

- **描述**: 使用 IP2Location.io API 获取 IP 地址地理位置和网络信息。

- **备注**: 官方参考, Python 开发 🐍, 云服务 ☁️, IP 地址信息 (IP2Location.io)。

---

## 🏃 体育与游戏

让 AI 能够访问体育赛事数据、游戏信息等

### 1. [CoderGamester/mcp-unity](https://github.com/CoderGamester/mcp-unity)

- **描述**: 用于 Unity3d 游戏引擎集成的 MCP 服务器，用于游戏开发。

- **备注**: 社区实现, TypeScript/C# 开发 📇#️⃣, 本地运行 🏠, Unity3D 集成。

### 2. [Coding-Solo/godot-mcp](https://github.com/Coding-Solo/godot-mcp)

- **描述**: 用于与 Godot 游戏引擎交互的 MCP 服务器，提供编辑、运行、调试和管理 Godot 项目中场景的工具。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Godot 引擎集成。

### 3. [kw510/strava-mcp](https://github.com/kw510/strava-mcp)

- **描述**: 用于 Strava (体育锻炼追踪应用) 的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Strava API 集成 (另一版本)。

### 4. [mikechao/balldontlie-mcp](https://github.com/mikechao/balldontlie-mcp)

- **描述**: 集成 balldontlie API，提供 NBA、NFL 和 MLB 的球员、球队和比赛信息。

- **备注**: 社区实现, TypeScript 开发 📇, 体育赛事数据 (balldontlie API)。

### 5. [pab1ito/chess-mcp](https://github.com/pab1it0/chess-mcp)

- **描述**: 访问 Chess.com 玩家数据、对局记录和其他公共信息，允许 AI 助手搜索和分析国际象棋信息。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Chess.com 数据。

### 6. [r-huijts/firstcycling-mcp](https://github.com/r-huijts/firstcycling-mcp)

- **描述**: 通过自然语言访问自行车比赛数据、结果和统计信息。功能包括从 firstcycling.com 检索出发名单、比赛结果和车手信息。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 自行车赛事数据 (firstcycling)。

### 7. [r-huijts/strava-mcp](https://github.com/r-huijts/strava-mcp)

- **描述**: 连接到 Strava API 的 MCP 服务器，提供通过 LLM 访问 Strava 数据的工具。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Strava API 集成。

### 8. [rishijatia/fantasy-pl-mcp](https://github.com/rishijatia/fantasy-pl-mcp/)

- **描述**: 用于实时 Fantasy Premier League 数据和分析工具的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Fantasy Premier League (英超梦幻足球)。

### 9. [sawa-zen/vrchat-mcp](https://github.com/sawa-zen/vrchat-mcp)

- **描述**: 与 VRChat API 交互的 MCP 服务器。可获取好友、世界、虚拟形象等信息。 (已在通讯协作部分列出)

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, VRChat API 交互。

---

## 🏛️ 艺术与文化

让 AI 能够访问艺术收藏、文化遗产、博物馆数据库等

### 1. [djalal/quran-mcp-server](https://github.com/djalal/quran-mcp-server)

- **描述**: 通过官方 REST API v4 与 Quran.com 语料库交互的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 古兰经文本交互。

### 2. [r-huijts/rijksmuseum-mcp](https://github.com/r-huijts/rijksmuseum-mcp)

- **描述**: Rijksmuseum API 集成，用于艺术品搜索、详情和收藏。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 荷兰国立博物馆艺术品。

### 3. [r-huijts/oorlogsbronnen-mcp](https://github.com/r-huijts/oorlogsbronnen-mcp)

- **描述**: Oorlogsbronnen (战争来源) API 集成，访问荷兰二战时期 (1940-1945) 的历史记录、照片和文件。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 荷兰二战历史资料。

### 4. [yuna0x0/anilist-mcp](https://github.com/yuna0x0/anilist-mcp)

- **描述**: 集成 AniList API 的 MCP 服务器，用于动漫和漫画信息。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 动漫/漫画信息 (AniList)。

---

## 🛠️ 其他实用工具与集成

包括计算器、API 集成、特定平台工具、聚合器、框架辅助等

### 1. [AgentRPC](https://github.com/agentrpc/agentrpc)

- **描述**: AgentRPC 官方集成，跨网络边界连接任何语言的任何函数。

- **备注**: 官方实现 (AgentRPC), Go/Python/TS/Rust 开发 🏎️🐍📇🦀, 跨语言函数调用。

### 2. [APIMatic MCP](https://github.com/apimatic/apimatic-validator-mcp)

- **描述**: APIMatic 官方集成，使用 APIMatic 验证 OpenAPI 规范。

- **备注**: 官方实现 (APIMatic), C# 开发 #️⃣, OpenAPI 规范验证。

### 3. [IBM wxflows](https://github.com/IBM/wxflows/tree/main/examples/mcp/javascript)

- **描述**: IBM 官方工具平台，为任何数据源构建、测试和部署工具。

- **备注**: 官方实现 (IBM), JavaScript 开发, 通用工具平台。

### 4. [Langfuse Prompt Management](https://github.com/langfuse/mcp-server-langfuse)

- **描述**: Langfuse 官方集成，用于协作编辑、版本控制、评估和发布提示的开源工具。(已在开发工具部分列出)

- **备注**: 官方实现 (Langfuse) 🎖️, Python 开发 🐍, 本地运行 🏠, Prompt 管理。

### 5. [UnifAI](https://github.com/unifai-network/unifai-mcp-server)

- **描述**: UnifAI 官方集成，使用 UnifAI 网络动态搜索和调用工具。

- **备注**: 官方实现 (UnifAI), Go 开发, 动态工具发现与调用。

### 6. [VeyraX](https://github.com/VeyraX/veyrax-mcp)

- **描述**: VeyraX 官方集成，单一工具控制 100+ API 集成和 UI 组件。

- **备注**: 官方实现 (VeyraX), Go 开发, 大规模 API/UI 控制。

### 7. [modelcontextprotocol/server-everything](https://github.com/modelcontextprotocol/servers/tree/main/src/everything)

- **描述**: 展示 MCP 协议所有功能的 MCP 服务器。

- **备注**: 官方参考, TypeScript 开发 📇, 本地运行 🏠, MCP 协议功能演示。

### 8. [Calculator](https://github.com/githejie/mcp-server-calculator)

- **描述**: 使 LLM 能够使用计算器进行精确的数值计算。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 基础计算器功能。

### 9. [Time](https://github.com/modelcontextprotocol/servers/tree/main/src/time)

- **描述**: 官方参考实现，提供时间和时区转换能力。

- **备注**: 官方参考, TypeScript 开发, 时间/时区工具。

### 10. [Sequential Thinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking)

- **描述**: 官方参考实现，通过思考序列进行动态和反思性问题解决。

- **备注**: 官方参考, TypeScript 开发, 复杂问题解决框架。

### 11. [OpenAPI AnyApi](https://github.com/baryhuang/mcp-server-any-openapi)

- **描述**: 使用内置语义搜索与大型 OpenAPI 文档交互，可自定义前缀。

- **备注**: 社区实现, Python 开发, 大型 OpenAPI 交互。

### 12. [OpenAPI Schema](https://github.com/hannesj/mcp-openapi-schema)

- **描述**: 让 LLM 在不增加上下文的情况下探索大型 OpenAPI 模式。

- **备注**: 社区实现, TypeScript 开发, 大型 OpenAPI 模式探索。

### 13. [GraphQL Schema](https://github.com/hannesj/mcp-graphql-schema)

- **描述**: 让 LLM 在不增加上下文的情况下探索大型 GraphQL 模式。

- **备注**: 社区实现, TypeScript 开发, 大型 GraphQL 模式探索。

### 14. [julien040/anyquery](https://github.com/julien040/anyquery)

- **描述**: 通过 SQL 查询 40+ 应用，并连接 PG/MySQL/SQLite 数据库。本地优先，注重隐私。

- **备注**: 社区实现, Go 开发 🏎️, 本地/云端 🏠☁️, 多应用/数据库查询聚合器。

### 15. [MetaMCP](https://github.com/metatool-ai/metatool-app)

- **描述**: MetaMCP 是统一的中间件 MCP 服务器，通过 GUI 管理您的 MCP 连接。

- **备注**: 社区实现, TypeScript 开发 📇, 云端/本地 ☁️🏠, 跨平台 🍎🪟🐧, MCP 连接管理 GUI。

### 16. [OpenMCP](https://github.com/wegotdocs/open-mcp)

- **描述**: 10 秒内将 Web API 转换为 MCP 服务器，并将其添加到开源注册表 [open-mcp.org](https://open-mcp.org)。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 跨平台 🍎🪟🐧, Web API 转 MCP 服务器。

### 17. [VeriTeknik/pluggedin-mcp-proxy](https://github.com/VeriTeknik/pluggedin-mcp-proxy)

- **描述**: 将多个 MCP 服务器组合到单个接口的综合代理服务器，具有广泛可见性功能 (工具/提示/资源/模板发现管理，调试平台)。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, MCP 代理与管理。

### 18. [AbdelStark/bitcoin-mcp](https://github.com/AbdelStark/bitcoin-mcp)

- **描述**: 使 AI 模型能与比特币交互的 MCP 服务器 (生成密钥/验证地址/解码交易/查询区块链等)。

- **备注**: 社区实现, 比特币交互 ₿.

### 19. [amidabuddha/unichat-mcp-server](https://github.com/amidabuddha/unichat-mcp-server)

- **描述**: 通过工具或预定义提示使用 MCP 协议向 OpenAI, MistralAI, Anthropic, xAI, Google AI 或 DeepSeek 发送请求。

- **备注**: 社区实现, Python/TypeScript 开发 🐍📇, 云服务 ☁️, 多 LLM API 调用。

### 20. [anaisbetts/mcp-installer](https://github.com/anaisbetts/mcp-installer)

- **描述**: 为您安装其他 MCP 服务器的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, MCP 服务器安装器。

### 21. [andybrandt/mcp-simple-openai-assistant](https://github.com/andybrandt/mcp-simple-openai-assistant)

- **描述**: 与 OpenAI Assistants 对话的 MCP (Claude 可以使用任何 GPT 模型作为其助手)。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 调用 OpenAI Assistants。

### 22. [andybrandt/mcp-simple-timeserver](https://github.com/andybrandt/mcp-simple-timeserver)

- **描述**: 允许检查客户端机器本地时间或从 NTP 服务器获取当前 UTC 时间的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 本地/云端 🏠☁️, 时间获取 (本地/NTP)。

### 23. [automation-ai-labs/mcp-link](https://github.com/automation-ai-labs/mcp-link)

- **描述**: 无缝集成任何带有 OpenAPI Schema 的 API 与 AI Agents。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, OpenAPI API 集成。

### 24. [baba786/phabricator-mcp-server](https://github.com/baba786/phabricator-mcp-server)

- **描述**: 与 Phabricator API 交互。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Phabricator 集成。

### 25. [billster45/mcp-chatgpt-responses](https://github.com/billster45/mcp-chatgpt-responses)

- **描述**: 让 Claude 与 ChatGPT 对话并使用其网页搜索能力的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Claude 调用 ChatGPT (含搜索)。

### 26. [blurrah/mcp-graphql](https://github.com/blurrah/mcp-graphql)

- **描述**: 允许 AI 查询 GraphQL 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, GraphQL 查询。

### 27. [chrishayuk/mcp-cli](https://github.com/chrishayuk/mcp-cli)

- **描述**: 用于测试 MCP 服务器的另一个 CLI 工具。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, MCP 测试 CLI。

### 28. [evalstate/mcp-hfspace](https://github.com/evalstate/mcp-hfspace)

- **描述**: 直接从 Claude 使用 HuggingFace Spaces。使用开源图像生成、聊天、视觉任务等。支持图像、音频和文本上传/下载。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Hugging Face Spaces 调用。

### 29. [future-audiences/wikimedia-enterprise-model-context-protocol](https://gitlab.wikimedia.org/repos/future-audiences/wikimedia-enterprise-model-context-protocol)

- **描述**: Wikipedia 文章查找 API。

- **备注**: 社区实现 (Wikimedia), Python 开发 🐍, 云服务 ☁️, Wikipedia 文章查找。

### 30. [gotoolkits/DifyWorkflow](https://github.com/gotoolkits/mcp-difyworkflow-server)

- **描述**: 用于查询和执行 Dify 工作流的工具。

- **备注**: 社区实现, Go 开发 🏎️, 云服务 ☁️, Dify 工作流执行。

### 31. [jagan-shanmugam/climatiq-mcp-server](https://github.com/jagan-shanmugam/climatiq-mcp-server)

- **描述**: 用于访问 Climatiq API 计算碳排放的 MCP 服务器。使 AI 助手能执行实时碳计算并提供气候影响见解。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 碳排放计算 (Climatiq API)。

### 32. [joshuarileydev/mac-apps-launcher-mcp-server](https://github.com/JoshuaRileyDev/mac-apps-launcher)

- **描述**: 在 macOS 上列出和启动应用程序的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, macOS 应用启动器 🍎。

### 33. [kenliao94/mcp-server-rabbitmq](https://github.com/kenliao94/mcp-server-rabbitmq)

- **描述**: 启用与 RabbitMQ 的交互（管理操作、消息入队/出队）。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, RabbitMQ 交互。

### 34. [kukapay/whattimeisit-mcp](https://github.com/kukapay/whattimeisit-mcp)

- **描述**: 精确告知当前时间的轻量级 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, 时间工具。

### 35. [kukapay/whereami-mcp](https://github.com/kukapay/whereami-mcp)

- **描述**: 基于当前 IP 精确告知您所在位置的轻量级 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, IP 定位。

### 36. [kukapay/whoami-mcp](https://github.com/kukapay/whoami-mcp)

- **描述**: 精确告知您是谁的轻量级 MCP 服务器。(可能指用户信息?)

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 用户信息(?)。

### 37. [lamemind/mcp-server-multiverse](https://github.com/lamemind/mcp-server-multiverse)

- **描述**: 中间件服务器，使同一 MCP 服务器的多个隔离实例能以独特的命名空间和配置独立共存。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, MCP 服务器多实例管理。

### 38. [lightconetech/mcp-gateway](https://github.com/lightconetech/mcp-gateway)

- **描述**: MCP SSE 服务器的网关演示。

- **备注**: 社区实现, TypeScript 开发 📇, MCP SSE 网关示例。

### 39. [magarcia/mcp-server-giphy](https://github.com/magarcia/mcp-server-giphy)

- **描述**: 通过 Giphy API 从 Giphy 的庞大库中搜索和检索 GIF。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Giphy GIF 搜索。

### 40. [marcelmarais/Spotify](https://github.com/marcelmarais/spotify-mcp-server)

- **描述**: 控制 Spotify 播放和管理播放列表。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, Spotify 控制。

### 41. [mcp-server-jfx](https://github.com/quarkiverse/quarkus-mcp-servers/tree/main/jfx)

- **描述**: 在 JavaFX 画布上绘图。

- **备注**: 社区实现 (Quarkiverse), Java 开发 ☕, 本地运行 🏠, JavaFX 绘图。

### 42. [mediar-ai/screenpipe](https://github.com/mediar-ai/screenpipe)

- **描述**: 本地优先系统，捕获屏幕/音频并带时间戳索引，SQL/嵌入存储，语义搜索，LLM 历史分析，事件触发动作。通过 NextJS 插件生态系统构建上下文感知 AI 代理。

- **备注**: 官方实现 (mediar.ai) 🎖️, Rust 开发 🦀, 本地运行 🏠, macOS 🍎, 屏幕/音频捕获与分析 RAG。

### 43. [mrexodia/user-feedback-mcp](https://github.com/mrexodia/user-feedback-mcp)

- **描述**: 简单的 MCP 服务器，在 Cline 和 Cursor 等工具中启用人机回圈工作流。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 人机回圈反馈。

### 44. [mrjoshuak/godoc-mcp](https://github.com/mrjoshuak/godoc-mcp)

- **描述**: Token 高效的 Go 文档服务器，为 AI 助手提供对包文档和类型的智能访问，无需读取整个源文件。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, Go 文档智能访问。

### 45. [mzxrai/mcp-openai](https://github.com/mzxrai/mcp-openai)

- **描述**: 与 OpenAI 最智能的模型聊天。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 调用 OpenAI 模型。

### 46. [NakaokaRei/swift-mcp-gui](https://github.com/NakaokaRei/swift-mcp-gui.git)

- **描述**: 可以执行键盘输入和鼠标移动等命令的 MCP 服务器。

- **备注**: 社区实现, 本地运行 🏠, macOS 🍎, GUI 自动化 (Swift)。

### 47. [nguyenvanduocit/all-in-one-model-context-protocol](https://github.com/nguyenvanduocit/all-in-one-model-context-protocol)

- **描述**: 面向开发者的有用工具集合，几乎包含工程师所需的一切：Confluence, Jira, Youtube, 运行脚本, 知识库 RAG, Fetch URL, 管理 Youtube 频道, 邮件, 日历, Gitlab。

- **备注**: 社区实现, Go 开发 🏎️, 本地运行 🏠, 开发者工具集。

### 48. [NON906/omniparser-autogui-mcp](https://github.com/NON906/omniparser-autogui-mcp)

- **描述**: 屏幕 GUI 的自动操作。

- **备注**: 社区实现, Python 开发 🐍, GUI 自动化。

### 49. [Open Strategy Partners Marketing Tools](https://github.com/open-strategy-partners/osp_marketing_tools)

- **描述**: Open Strategy Partners 的一套营销工具，包括写作风格、编辑规范和产品营销价值图创建。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 营销工具套件。

### 50. [paulotaylor/voyp-mcp](https://github.com/paulotaylor/voyp-mcp)

- **描述**: VOYP - Voice Over Your Phone MCP 服务器，用于拨打电话。

- **备注**: 社区实现, TypeScript 开发 📇, 电话拨打。

### 51. [pierrebrunelle/mcp-server-openai](https://github.com/pierrebrunelle/mcp-server-openai)

- **描述**: 直接从 Claude 使用 MCP 协议查询 OpenAI 模型。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Claude 调用 OpenAI。

### 52. [pskill9/hn-server](https://github.com/pskill9/hn-server)

- **描述**: 解析 news.ycombinator.com (Hacker News) 的 HTML 内容，并为不同类型的故事提供结构化数据。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Hacker News 内容解析。

### 53. [pskill9/website-downloader](https://github.com/pskill9/website-downloader)

- **描述**: 使用 wget 下载整个网站的 MCP 服务器。保留网站结构并将链接转换为本地工作。

- **备注**: 社区实现, Go 开发 🚀, 网站下载器 (wget)。

### 54. [PV-Bhat/vibe-check-mcp-server](https://github.com/PV-Bhat/vibe-check-mcp-server)

- **描述**: 通过调用 "Vibe-check" Agent 来确保用户对齐，防止级联错误和范围蔓延的 MCP 服务器。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, Agent 对齐检查。

### 55. [pwh-pwh/cal-mcp](https://github.com/pwh-pwh/cal-mcp)

- **描述**: 用于数学表达式计算的 MCP 服务器。

- **备注**: 社区实现, 数学计算。

### 56. [pyroprompts/any-chat-completions-mcp](https://github.com/pyroprompts/any-chat-completions-mcp)

- **描述**: 与任何其他 OpenAI SDK 兼容的聊天完成 API 聊天，如 Perplexity, Groq, xAI 等。

- **备注**: 社区实现, 任意 OpenAI 兼容 API 调用。

### 57. [reeeeemo/ancestry-mcp](https://github.com/reeeeemo/ancestry-mcp)

- **描述**: 允许 AI 读取 .ged 文件和遗传数据。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, 家族史/遗传数据读取 (.ged)。

### 58. [rusiaaman/wcgw](https://github.com/rusiaaman/wcgw/blob/main/src/wcgw/client/mcp_server/Readme.md)

- **描述**: 自主 Shell 执行、计算机控制和编码代理 (Mac)。

- **备注**: 社区实现, Python 开发 🐍, 本地运行 🏠, macOS 🍎, 自主控制/编码代理。

### 59. [SecretiveShell/MCP-wolfram-alpha](https://github.com/SecretiveShell/MCP-wolfram-alpha)

- **描述**: 用于查询 Wolfram Alpha API 的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Wolfram Alpha 查询。

### 60. [Seym0n/tiktok-mcp](https://github.com/Seym0n/tiktok-mcp)

- **描述**: 与 TikTok 视频交互。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, TikTok 交互。

### 61. [tomekkorbak/oura-mcp-server](https://github.com/tomekkorbak/oura-mcp-server)

- **描述**: 用于 Oura (睡眠追踪应用) 的 MCP 服务器。

- **备注**: 社区实现, Python 开发 🐍, 云服务 ☁️, Oura 睡眠数据。

### 62. [wanaku-ai/wanaku](https://github.com/wanaku-ai/wanaku)

- **描述**: Wanaku MCP 路由器是基于 SSE 的 MCP 服务器，提供可扩展的路由引擎，允许将企业系统与 AI Agents 集成。

- **备注**: 官方实现 (Wanaku AI), 云端/本地 🏠☁️, MCP 路由引擎。

### 63. [wong2/mcp-cli](https://github.com/wong2/mcp-cli)

- **描述**: 用于测试 MCP 服务器的 CLI 工具 (另一版本)。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, MCP 测试 CLI (TS)。

### 64. [ws-mcp](https://github.com/nick1udwig/ws-mcp)

- **描述**: 用 WebSocket 包装 MCP 服务器 (用于 [kitbitz](https://github.com/nick1udwig/kibitz))。

- **备注**: 社区实现, WebSocket 包装器。

### 65. [ZeparHyfar/mcp-datetime](https://github.com/ZeparHyfar/mcp-datetime)

- **描述**: 提供各种格式的日期和时间功能的 MCP 服务器。

- **备注**: 社区实现, 日期时间工具。

### 66. [zueai/mcp-manager](https://github.com/zueai/mcp-manager)

- **描述**: 用于安装和管理 Claude Desktop App 的 MCP 服务器的简单 Web UI。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, MCP 服务器管理 Web UI。

### 67. [HenryHaoson/Yuque-MCP-Server](https://github.com/HenryHaoson/Yuque-MCP-Server)

- **描述**: 用于集成语雀 API 的 MCP 服务器，允许 AI 模型管理文档、与知识库交互、搜索内容和访问语雀平台的分析数据。

- **备注**: 社区实现, TypeScript 开发 📇, 云服务 ☁️, 语雀 API 集成。

### 68. [ttommyth/interactive-mcp](https://github.com/ttommyth/interactive-mcp)

- **描述**: 通过在 MCP 循环中直接添加本地用户提示和聊天功能，实现交互式 LLM 工作流。

- **备注**: 社区实现, TypeScript 开发 📇, 本地运行 🏠, 人机交互工作流。

---

