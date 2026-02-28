# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

这是一个个人学习笔记仓库，用于整理和存储各类学习文档。

## 目录结构

- `programming/` - 编程语言笔记 (Python, JavaScript, Go, Rust 等)
- `ai-ml/` - 人工智能与机器学习笔记
- `system-design/` - 系统设计与架构笔记
- `books/` - 书籍笔记和摘要
- `notes/` - 其他学习笔记
- `projects/` - 学习项目代码
- `resources/` - 学习资源、链接、文档

## 规范

- 笔记使用 Markdown 格式
- 代码示例可放在 `.md` 文件中或独立代码文件
- **禁止在任何文件中包含敏感信息**（如 API tokens、密码、密钥、个人凭证等），配置示例应使用占位符（如 `your_token_here`、`<YOUR_API_KEY>`）

## 工作流程规范

### 生成新文档后的必须操作

每次创建、删除或大幅修改文档后，**必须**执行以下操作：

1. **更新 README.md** - 同步文档目录结构的变化
2. **Git 提交** - 将更改提交到仓库

> 重要：这是强制性的最后步骤，不可跳过。
