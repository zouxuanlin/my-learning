# DeerFlow - 开源超级智能体框架

## 概述

DeerFlow（Deep Exploration and Efficient Research Flow）是由字节跳动技术团队开发的开源超级智能体框架。它是一个基于LangGraph和LangChain构建的智能体运行时环境，能够协调子智能体、内存和沙箱来执行各种复杂任务。

DeerFlow 2.0 是一个从头开始重写的版本，与1.x版本没有代码共享。它不再仅仅是一个深度研究框架，而是演变成了一个完整的超级智能体运行时环境（Super Agent Harness）。

## 核心特性

### 1. 技能与工具系统（Skills & Tools）

- **技能模块化**：DeerFlow使用结构化的技能模块（SKILL.md文件）来定义工作流程、最佳实践和支持资源
- **渐进式加载**：技能只在需要时加载，保持上下文窗口精简
- **高度可扩展**：可以添加自定义技能，替换内置技能，或组合成复合工作流
- **内置技能**：包括研究、报告生成、幻灯片创建、网页生成、图像和视频生成等

### 2. 子智能体系统（Sub-Agents）

- **任务分解**：主智能体可以动态生成子智能体来处理复杂任务
- **并行执行**：子智能体可以并行运行，提高效率
- **结构化结果**：子智能体返回结构化结果，主智能体进行合成
- **隔离上下文**：每个子智能体运行在独立的上下文中，避免干扰

### 3. 沙箱与文件系统（Sandbox & File System）

- **隔离执行环境**：每个任务在独立的Docker容器中运行
- **完整文件系统**：包含技能目录、工作区、上传和输出目录
- **安全执行**：支持代码执行、文件操作、命令行工具等
- **零污染**：会话之间完全隔离，无数据污染

### 4. 上下文工程（Context Engineering）

- **上下文管理**：通过摘要、文件系统卸载等方式管理长上下文
- **子智能体隔离**：确保子智能体专注于当前任务
- **高效上下文利用**：避免上下文窗口溢出

### 5. 长期记忆（Long-Term Memory）

- **持久化记忆**：跨会话记住用户偏好、配置文件和累积知识
- **本地存储**：记忆数据存储在本地，用户完全控制
- **个性化体验**：随着使用时间增加，智能体对用户的了解越来越深入

## 技术架构

### 后端架构

```
                        ┌──────────────────────────────────────┐
                        │          Nginx (Port 2026)           │
                        │      Unified reverse proxy           │
                        └───────┬──────────────────┬───────────┘
                                │                  │
              /api/langgraph/*  │                  │  /api/* (other)
                                ▼                  ▼
               ┌────────────────────┐  ┌────────────────────────┐
               │ LangGraph Server   │  │   Gateway API (8001)   │
               │    (Port 2024)     │  │   FastAPI REST         │
               │                    │  │                        │
               │ ┌────────────────┐ │  │ Models, MCP, Skills,   │
               │ │  Lead Agent    │ │  │ Memory, Uploads,       │
               │ │  ┌──────────┐  │ │  │ Artifacts              │
               │ │  │Middleware│  │ │  └────────────────────────┘
               │ │  │  Chain   │  │ │
               │ │  └──────────┘  │ │
               │ │  ┌──────────┐  │ │
               │ │  │  Tools   │  │ │
               │ │  └──────────┘  │ │
               │ │  ┌──────────┐  │ │
               │ │  │Subagents │  │ │
               │ │  └──────────┘  │ │
               │ └────────────────┘ │
               └────────────────────┘
```

### 中间件链（Middleware Chain）

DeerFlow使用9个中间件按严格顺序执行：

1. **ThreadDataMiddleware** - 创建每线程隔离目录
2. **UploadsMiddleware** - 注入上传文件到对话上下文
3. **SandboxMiddleware** - 获取沙箱环境用于代码执行
4. **SummarizationMiddleware** - 在接近令牌限制时减少上下文
5. **TodoListMiddleware** - 在计划模式下跟踪多步骤任务
6. **TitleMiddleware** - 自动生成对话标题
7. **MemoryMiddleware** - 为异步记忆提取排队对话
8. **ViewImageMiddleware** - 为视觉模型注入图像数据
9. **ClarificationMiddleware** - 拦截澄清请求并中断执行

### 工具生态系统

- **沙箱工具**：`bash`, `ls`, `read_file`, `write_file`, `str_replace`
- **内置工具**：`present_files`, `ask_clarification`, `view_image`, `task`（子智能体）
- **社区工具**：Tavily（网络搜索）、Jina AI（网页抓取）、Firecrawl（爬虫）、DuckDuckGo（图像搜索）
- **MCP工具**：任何Model Context Protocol服务器
- **技能工具**：特定领域的注入工作流

## 快速开始

### 安装与配置

```bash
# 克隆仓库
git clone https://github.com/bytedance/deer-flow.git
cd deer-flow

# 生成配置文件
make config

# 编辑config.yaml配置模型
models:
  - name: gpt-4o
    display_name: GPT-4o
    use: langchain_openai:ChatOpenAI
    model: gpt-4o
    api_key: $OPENAI_API_KEY
    supports_thinking: false
    supports_vision: true

# 设置API密钥
export OPENAI_API_KEY="your-api-key-here"
```

### 运行方式

#### Docker方式（推荐）

```bash
make docker-init    # 初始化（仅首次或镜像更新时）
make docker-start   # 启动服务
```

访问地址：http://localhost:2026

#### 本地开发

```bash
make check          # 检查依赖
make install        # 安装依赖
make dev            # 启动开发服务
```

## 前端技术栈

- **框架**：Next.js 16 + App Router
- **UI库**：React 19, Tailwind CSS 4, Shadcn UI, MagicUI, React Bits
- **AI集成**：LangGraph SDK, Vercel AI Elements

## 目录结构

```
deer-flow/
├── backend/                # 后端服务
│   ├── src/                # 源代码
│   │   ├── agents/         # 智能体系统
│   │   ├── gateway/        # Gateway API
│   │   ├── sandbox/        # 沙箱执行
│   │   ├── subagents/      # 子智能体
│   │   └── tools/          # 工具系统
├── frontend/               # 前端应用
│   ├── src/app/            # Next.js页面
│   ├── src/components/     # React组件
│   └── src/core/           # 核心业务逻辑
├── skills/                 # 技能目录
│   └── public/             # 公共技能
│       ├── deep-research/  # 深度研究技能
│       ├── ppt-generation/ # PPT生成技能
│       └── ...             # 其他技能
└── docker/                 # Docker配置
```

## 技能示例：深度研究技能

深度研究技能是DeerFlow的核心技能之一，提供系统性的网络研究方法论：

### 研究方法论

1. **广泛探索阶段**
   - 初始调查：搜索主要话题了解整体背景
   - 识别维度：从初始结果中识别关键子话题、主题、角度
   - 地图绘制：记录不同观点、利益相关者或视角

2. **深度挖掘阶段**
   - 特定查询：针对每个子话题进行精准搜索
   - 多种表述：尝试不同的关键词组合
   - 完整内容获取：使用web_fetch读取重要来源的完整内容
   - 跟踪引用：当来源提到其他重要资源时，继续搜索

3. **多样性与验证**
   - 事实与数据：具体证据
   - 示例与案例：真实应用场景
   - 专家观点：权威视角
   - 趋势与预测：未来方向
   - 比较分析：上下文和替代方案
   - 挑战与批评：平衡观点

4. **综合检查**
   - 是否从至少3-5个不同角度进行了搜索？
   - 是否获取并阅读了最重要的完整来源？
   - 是否有具体数据、示例和专家观点？
   - 是否探索了正面和挑战/限制？
   - 信息是否最新且来自权威来源？

## 社区与贡献

- **GitHub仓库**：https://github.com/bytedance/deer-flow
- **官方网站**：https://deerflow.tech/
- **许可证**：MIT License
- **Star数**：21,000+（截至2026年2月）

DeerFlow在2026年2月28日发布2.0版本后，在GitHub Trending上获得了第一名的位置，获得了社区的广泛关注和认可。

## 与其他框架的关系

- **基于LangGraph 1.0构建**：相当于LangGraph的"超级智能体外壳"
- **与LangChain深度集成**：利用LangChain的LLM抽象和工具系统
- **MCP协议支持**：支持Model Context Protocol标准，可以集成各种MCP服务器

## 使用场景

1. **深度研究**：自动进行多角度、多来源的网络研究
2. **内容生成**：生成报告、PPT、网页、图像、视频等内容
3. **数据分析**：处理和分析上传的数据文件
4. **代码生成**：编写、测试和部署代码
5. **自动化工作流**：执行复杂的多步骤任务

## 总结

DeerFlow代表了AI智能体发展的一个重要方向：从简单的聊天机器人向具有实际执行能力的超级智能体演进。通过提供完整的运行时环境、丰富的工具集和灵活的技能系统，DeerFlow使得开发者能够构建真正有用的AI应用，而不仅仅是对话界面。