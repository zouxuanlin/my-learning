# Claude Code Skills 参考资料

本文档整理了 Claude Code 中所有可用的 Skills 和使用方法。

---

## 目录

1. [内置命令](#1-内置命令)
2. [文档技能 (document-skills)](#2-文档技能)
3. [技能使用示例](#3-技能使用示例)

---

## 1. 内置命令

### 1.1 基础命令

| 命令 | 描述 |
|------|------|
| `/help` | 显示帮助信息和可用命令列表 |
| `/clear` | 清除当前对话的上下文 |
| `/mcp` | 查看和管理 MCP 服务器连接 |

### 1.2 Git 相关命令

| 命令 | 描述 |
|------|------|
| `/commit` | 创建 git 提交 |
| `/git` | 执行 git 操作 |

### 1.3 代码审查

| 命令 | 描述 |
|------|------|
| `/review-pr` | 审查 Pull Request |

---

## 2. 文档技能 (document-skills)

文档技能是 Claude Code 中一类特殊的技能，用于处理各种文档和创作任务。

### 2.1 文档创作类

#### docx
处理 Microsoft Word 文档 (.docx)

**使用场景**：
- 创建专业的 Word 文档
- 读取和提取 .docx 文件内容
- 编辑现有文档
- 添加目录、页眉页脚
- 处理追踪更改和评论

**触发方式**：
- "帮我创建一个 Word 文档..."
- "读取这个 .docx 文件..."
- "/docx"

---

#### pptx
处理 PowerPoint 演示文稿 (.pptx)

**使用场景**：
- 创建幻灯片演示文稿
- 读取和解析现有 PPTX
- 编辑修改演示文稿
- 提取演讲者备注
- 合并或拆分幻灯片

**触发方式**：
- "帮我做一个 PPT..."
- "创建一个演示文稿..."
- "/pptx"

---

#### pdf
处理 PDF 文件

**使用场景**：
- 读取 PDF 内容
- 提取文本和表格
- 合并/拆分 PDF
- 旋转页面
- 添加水印
- 填充 PDF 表单
- OCR 识别扫描 PDF

**触发方式**：
- "读取这个 PDF..."
- "合并这些 PDF 文件..."
- "/pdf"

---

#### xlsx
处理电子表格 (.xlsx, .xlsm, .csv, .tsv)

**使用场景**：
- 创建 Excel 电子表格
- 读取和编辑现有表格
- 添加公式和图表
- 数据清洗和格式化
- 转换 CSV/TSV 格式

**触发方式**：
- "帮我创建一个 Excel 表格..."
- "分析这个 xlsx 文件..."
- "/xlsx"

---

### 2.2 设计类

#### frontend-design
创建高质量前端界面

**使用场景**：
- 构建 Web 组件和页面
- 创建仪表板和着陆页
- React 组件开发
- HTML/CSS 布局
- 使用 Tailwind CSS、shadcn/ui

**触发方式**：
- "帮我设计一个..."
- "创建一个漂亮的界面..."
- "/frontend-design"

---

#### canvas-design
创建静态视觉设计

**使用场景**：
- 设计海报
- 创建 .png/.pdf 文档
- 制作视觉设计稿
- 应用设计原则

**触发方式**：
- "设计一张海报..."
- "创建一个设计图..."
- "/canvas-design"

---

#### brand-guidelines
应用品牌视觉规范

**使用场景**：
- 应用 Anthropic 品牌规范
- 使用品牌颜色和字体
- 确保视觉一致性

**触发方式**：
- "用品牌风格设计..."
- "/brand-guidelines"

---

#### theme-factory
为主题样式提供工具

**使用场景**：
- 为幻灯片/文档应用主题
- 10 种预设主题
- 自定义主题生成

**触发方式**：
- "用 xx 主题美化这个..."
- "/theme-factory"

---

### 2.3 专业技术类

#### mcp-builder
创建 MCP 服务器

**使用场景**：
- 构建 MCP 服务器
- 集成外部 API
- 使用 FastMCP (Python) 或 MCP SDK (Node/TypeScript)

**触发方式**：
- "帮我创建一个 MCP 服务器..."
- "/mcp-builder"

---

#### web-artifacts-builder
创建复杂 HTML artifacts

**使用场景**：
- 多组件 Web 应用
- 需要状态管理的界面
- 使用 React、Tailwind、shadcn/ui

**触发方式**：
- "创建一个复杂的 Web 应用..."
- "/web-artifacts-builder"

---

#### webapp-testing
Web 应用测试工具

**使用场景**：
- 使用 Playwright 测试
- 前端功能验证
- 调试 UI 行为
- 浏览器截图
- 查看浏览器日志

**触发方式**：
- "测试这个 Web 应用..."
- "/webapp-testing"

---

#### algorithmic-art
创建算法艺术

**使用场景**：
- 使用 p5.js 创作
- 生成艺术
- 流场和粒子系统
- 种子随机性
- 交互式参数探索

**触发方式**：
- "用代码创作艺术..."
- "生成算法艺术..."
- "/algorithmic-art"

---

#### slack-gif-creator
创建 Slack 动画 GIF

**使用场景**：
- 为 Slack 制作 GIF
- 动画创作
- GIF 约束优化

**触发方式**：
- "为 Slack 做个 GIF..."
- "/slack-gif-creator"

---

### 2.4 沟通协作类

#### internal-comms
撰写内部沟通文档

**使用场景**：
- 状态报告
- 领导更新
- 公司通讯
- FAQ 文档
- 事件报告
- 项目更新

**触发方式**：
- "帮我写一个状态报告..."
- "/internal-comms"

---

#### doc-coauthoring
协作文档创作工作流

**使用场景**：
- 技术文档撰写
- 提案编写
- 技术规范
- 决策文档

**触发方式**：
- "帮我写一个文档..."
- "/doc-coauthoring"

---

#### skill-creator
创建新技能

**使用场景**：
- 扩展 Claude 功能
- 定义专业工作流程
- 集成特定工具

**触发方式**：
- "帮我创建一个新的技能..."
- "/skill-creator"

---

## 3. 技能使用示例

### 3.1 使用 commit 技能

```
/commit -m "修复登录验证逻辑"
```

### 3.2 使用 review-pr 技能

```
/review-pr 123
```

### 3.3 使用 docx 技能

```
帮我创建一个项目提案文档，包含以下内容：
- 项目背景
- 目标
- 时间线
```

### 3.4 使用 frontend-design 技能

```
/frontend-design 帮我创建一个待办事项应用的 UI，要求：
- 简洁现代的设计
- 深色模式支持
- 响应式布局
```

### 3.5 使用 pdf 技能

```
/pdf 读取这个文件并提取所有表格数据
```

### 3.6 使用 xlsx 技能

```
帮我分析这个销售数据表格，创建一个图表展示月度趋势
```

---

## 4. 技能调用最佳实践

1. **明确任务**：清晰描述你要完成的任务
2. **提供上下文**：包含必要的背景信息
3. **指定格式**：说明期望的输出格式
4. **迭代优化**：根据需要调整和 refinement

---

## 参考资源

- [Claude Code 官方文档](https://claude.ai/code/docs)
- [MCP 官方文档](https://modelcontextprotocol.io/)

---

*最后更新：2026-02-28*
