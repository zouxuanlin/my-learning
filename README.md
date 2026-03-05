# My Learning Repository

个人学习笔记仓库，用于整理和存储各类学习文档。

## 目录结构

```
my-learning/
├── ai-ml/                      # 人工智能与机器学习笔记
│   ├── ai-tools/               # AI 工具使用指南 (NotebookLM 等)
│   ├── mcp-servers/            # MCP 服务器文档与配置
│   ├── ml-theory/              # 机器学习理论 (预留)
│   └── security/               # AI/系统安全研究 (密码学、认证、安全协议)
├── dev-tools/                  # 开发工具与配置
│   ├── claude-code/            # Claude Code 相关文档 (MCP/Skills)
│   ├── git/                    # Git 相关文档
│   ├── hardware/               # 硬件设备使用指南 (相机/外设等)
│   ├── openclaw/               # OpenClaw 相关文档 (配置/技能/用例)
│   └── troubleshooting/        # 问题解决方案与故障排除
├── programming/                # 编程语言相关笔记 (Python, JavaScript, Go, Rust 等)
├── system-design/              # 系统设计与架构笔记
├── books/                      # 书籍笔记和摘要
├── docs/                       # 官方文档备份
│   └── openclaw-official/      # OpenClaw 官方文档
├── presentations/              # 演示文稿
└── projects/                   # 学习项目代码
```

## 规范

- 笔记使用 Markdown 格式
- 代码示例可放在 `.md` 文件中或独立代码文件
- **禁止在任何文件中包含敏感信息**（如 API tokens、密码、密钥、个人凭证等），配置示例应使用占位符（如 `your_token_here`、`<YOUR_API_KEY>`）
- **新增文档时必须放到合适的目录下**：
  - MCP 服务器文档 → `ai-ml/mcp-servers/`
  - AI 工具指南 → `ai-ml/ai-tools/`
  - Claude Code/Skills 文档 → `dev-tools/claude-code/`
  - OpenClaw 文档 → `dev-tools/openclaw/`
  - 官方文档备份 → `docs/openclaw-official/`
  - 演示文稿 → `presentations/`
  - 问题解决方案 → `dev-tools/troubleshooting/`
  - 编程语言笔记 → `programming/`
  - 系统设计笔记 → `system-design/`
  - 书籍笔记 → `books/`
  - 项目代码 → `projects/`
- **如有必要可以创建新的子目录**以更好地组织内容

## 工作流程规范

### 新增文档时

1. **判断文档主题**，选择合适的目录：
   - 参考上方「目录结构」的分类规则
   - 如现有目录不适用，可创建新的子目录
2. **创建文档**到目标目录
3. **更新 README.md**（如新增目录或重要文档）
4. **Git 提交**

### 生成新文档后的必须操作

每次创建、删除或大幅修改文档后，**必须**执行以下操作：

1. **更新 README.md** - 同步文档目录结构的变化
2. **Git 提交** - 将更改提交到仓库

> 重要：这是强制性的最后步骤，不可跳过。

## 近期更新记录

- 2026-03-03: 添加阿里云通义千问大模型对比分析PPT
- 2026-03-03: 添加 OpenClaw 官方文档备份
- 2026-03-03: 添加网页应用需求文档模板
- 2026-03-03: 添加 OpenClaw Agent 提示词技巧整理文档
- 2026-03-02: 添加 OpenClaw 快照恢复指南文档
- 2026-03-02: 重组目录结构，将 papers/cryptography 移动到 ai-ml/security/
- 2026-03-01: 添加 DJI Pocket 3 完整使用指南（规格/设置/拍摄技巧/配件推荐）
- 2026-03-01: 添加 Rust 编程语言学习资料（学习路线/快速入门/Crate 推荐/进度跟踪）
- 2026-03-01: 添加 OpenClaw 使用案例汇总、配置指南、技能开发指南文档
- 2026-02-28: 添加 GitHub MCP 连接失败解决方案文档
- 2026-02-28: 重组目录结构，将 resources/solutions/plans/notes 合并到 dev-tools/
- 2026-02-28: 添加 Awesome-MCP-ZH MCP 服务器分类整理文档（20 分类 533 个项目）
- 2026-02-28: 添加 Claude CLI 中 Browser MCP 无法调用问题解决方案文档
- 2026-02-28: 添加 macOS Zsh 拷贝粘贴卡顿解决方案文档
- 2026-02-28: 添加 Browser MCP 浏览器自动化完整指南文档
- 2026-02-28: 添加 Google NotebookLM 完整指南文档
- 2026-02-28: 添加 Git Push 超时解决方案文档
- 2026-02-28: 添加 MCP 与 Skills 组织指南、配置示例、Skills 参考文档
- 2026-02-27: 添加 GitHub MCP Server 集成文档
- 2026-02-27: 初始化目录结构

### 问题解决方案

| 文档 | 描述 |
|------|------|
| [Git Push 超时解决方案](./dev-tools/troubleshooting/git-push-timeout-solutions.md) | 解决 Git 推送超时问题的 10 种方法 |
| [Zsh 拷贝粘贴卡顿解决方案](./dev-tools/troubleshooting/zsh-copy-paste-lag-solution.md) | 解决 macOS zsh 终端拷贝命令执行卡顿问题 |
| [Browser MCP 无法调用解决方案](./dev-tools/troubleshooting/claude-mcp-browsermcp-solution.md) | 解决 Claude CLI 中 Browser MCP 配置无法识别的问题 |
| [GitHub MCP 连接失败解决方案](./dev-tools/troubleshooting/github-mcp-connection-fix.md) | 解决 GitHub MCP Server 连接失败问题 |

### AI 工具与 MCP 服务器

| 文档 | 描述 |
|------|------|
| [Step3.5 Flash 模型介绍](./ai-ml/ai-tools/step3.5-flash-model.md) | 阶跃星辰 Step3.5 Flash 开源大语言模型技术特点与优势分析 |
| [Google NotebookLM 完整指南](./ai-ml/ai-tools/notebooklm.md) | NotebookLM 功能、架构、使用技巧全解析 |
| [Browser MCP 完整指南](./ai-ml/mcp-servers/browser-mcp-guide.md) | 浏览器自动化 MCP 服务器配置与使用 |
| [Browser MCP 文档](./ai-ml/mcp-servers/browser-mcp.md) | Browser MCP 相关文档 |
| [MCP 服务器分类速查表](./ai-ml/mcp-servers/mcp-servers-quick-reference.md) | 20 分类 533 个 MCP 服务器速查索引 |
| [MCP 服务器完整列表](./ai-ml/mcp-servers/awesome-mcp-zh-servers.md) | Awesome-MCP-ZH 完整 MCP 服务器整理 |

### OpenClaw 相关

| 文档 | 描述 |
|------|------|
| [OpenClaw 使用案例汇总](./dev-tools/openclaw/use-cases.md) | 10 大类使用场景与配置示例 |
| [OpenClaw 配置指南](./dev-tools/openclaw/config-guide.md) | 完整配置模板与最佳实践 |
| [OpenClaw 技能开发指南](./dev-tools/openclaw/skill-development.md) | 技能开发教程与示例 |
| [OpenClaw 子Agent创建指南](./dev-tools/openclaw/subagent-creation-guide.md) | 子Agent概念、创建方法、配置参数和最佳实践 |
| [OpenClaw 快照恢复指南](./dev-tools/openclaw/snapshot-recovery.md) | 独立快照备份与恢复方案 |
| [OpenClaw Agent 提示词技巧整理](./dev-tools/openclaw/openclaw-agent-prompt-techniques.md) | OpenClaw Agent 提示词工程最佳实践 |

### 官方文档备份

| 文档 | 描述 |
|------|------|
| [OpenClaw 官方文档](./docs/openclaw-official/README.md) | 从 docs.openclaw.ai 下载的官方文档内容 |

### 系统设计

| 文档 | 描述 |
|------|------|
| [网页应用需求文档模板](./system-design/web-app-requirements-template.md) | 完整的网页应用需求分析模板 |

### 演示文稿

| 文档 | 描述 |
|------|------|
| [阿里云通义千问大模型对比分析](./presentations/aliyun-qwen-models-comparison.md) | Qwen-Max/Plus/Turbo/Long 四种模型的优劣对比分析 |

### 编程语言

| 文档 | 描述 |
|------|------|
| [Rust 学习资料](./programming/rust/README.md) | Rust 语言学习路线、资源和实践指南 |
| [Rust 快速入门](./programming/rust/quick-start.md) | Rust 安装、第一个程序和核心概念速查 |
| [Rust 常用 Crate](./programming/rust/crates.md) | 精选 Rust 库推荐与使用场景 |
| [Rust 学习进度跟踪](./programming/rust/learning-progress.md) | 学习清单和进度记录模板 |

### 硬件设备

| 文档 | 描述 |
|------|------|
| [DJI Pocket 3 完整使用指南](./dev-tools/hardware/pocket-3-guide.md) | Pocket 3 规格/设置/拍摄技巧/配件推荐 |

### AI/系统安全

| 文档 | 描述 |
|------|------|
| [量子密码算法研究报告](./ai-ml/quantum-cryptography-report.md) | 量子密钥分发(QKD)与后量子密码(PQC)全面分析 |
| [密码学与安全论文阅读](./ai-ml/security/README.md) | 密码学、认证、AI 安全领域论文追踪 |
| [每日论文模板](./ai-ml/security/daily-paper-template.md) | 论文阅读笔记模板 |

### 计划与规划

| 文档 | 描述 |
|------|------|
| [GitHub 设置计划](./dev-tools/github-setup-plan.md) | GitHub 相关设置与规划 |