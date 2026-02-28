# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

这是一个个人学习笔记仓库，用于整理和存储各类学习文档。

## 目录结构

- `ai-ml/` - 人工智能与机器学习笔记
  - `mcp-servers/` - MCP 服务器文档与配置
  - `ai-tools/` - AI 工具使用指南 (NotebookLM 等)
  - `ml-theory/` - 机器学习理论
- `dev-tools/` - 开发工具与配置
  - `claude-code/` - Claude Code 相关文档 (MCP/Skills)
  - `git/` - Git 相关文档
  - `troubleshooting/` - 问题解决方案与故障排除
- `programming/` - 编程语言笔记 (Python, JavaScript, Go, Rust 等)
- `system-design/` - 系统设计与架构笔记
- `books/` - 书籍笔记和摘要
- `projects/` - 学习项目代码

## 规范

- 笔记使用 Markdown 格式
- 代码示例可放在 `.md` 文件中或独立代码文件
- **禁止在任何文件中包含敏感信息**（如 API tokens、密码、密钥、个人凭证等），配置示例应使用占位符（如 `your_token_here`、`<YOUR_API_KEY>`）
- **新增文档时必须放到合适的目录下**：
  - MCP 服务器文档 → `ai-ml/mcp-servers/`
  - AI 工具指南 → `ai-ml/ai-tools/`
  - Claude Code/Skills 文档 → `dev-tools/claude-code/`
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
