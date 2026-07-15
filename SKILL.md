---
name: github-repo-infrastructure
description: Use when creating or updating a GitHub repository's README, SECURITY.md, issue templates, LICENSE, or other community health files. Use when initializing a new repository, when the user asks to generate project documentation or write a README, or when checking existing README for spec compliance violations.
---

# GitHub 仓库基础设施

## Overview

一站式 GitHub 仓库基础设施：README 正像食谱、SECURITY.md 安全策略、Issue 模板、GPL-3.0 许可证。所有模板保持与 [ServerHarbor](https://github.com/sunnyhmz7010/ServerHarbor) 一致的风格和联系方式。

## When to Use

- 新建 GitHub 仓库时初始化基础设施文件（README、SECURITY.md、ISSUE_TEMPLATE、LICENSE）
- 用户要求"生成 README""写项目文档""添加安全策略""设置 Issue 模板"
- 补全仓库的 Issue 模板、PR 模板或社区健康文件
- 检查现有 README 是否符合规范骨架并修复

## README 规范（正像食谱）

README 不是规则清单，是**可直接填空的 HTML 模板**。你只替换 `{占位符}`，不增删改任何 HTML 结构、Emoji 前缀或章节顺序。

### 强制约束

1. **头部必须用 HTML**：`<div align="center"><h1>{项目名}</h1><p>{描述}</p></div>`，**严禁用 Markdown `# 标题` 代替**
2. **一句话描述（`<p>` 内）**：15-40 字的完整句子，说明项目功能或解决问题。**严禁用 `·` 分隔关键词或列举特性**
3. **所有二/三/四级标题必须带 Emoji 前缀**，按下方固定顺序排列。**不增删改顺序，不跳过非可选章节**
4. **徽章和链接必须用 `<p align="center">` 包裹**。`align="center"` 属性不可省略
5. **链接行**：每个链接是独立的 `[文本](URL)` 格式，多个之间用 ` · ` 分隔。**严禁转义方括号为 `\[` `\]`**
6. **代码块必须是可直接复制执行的原生命令**，不含 `rtk` 前缀
7. **底部固定签名**：`<div align="center"><sub>Built with ❤️ by Sunny</sub></div>`

### 章节顺序（固定，不可调换）

| 序号 | 章节标题 | 必须 | 说明 |
|------|---------|------|------|
| 1 | （头部 HTML 块） | ✅ | `<div align="center">` + `<h1>` + `<p>` |
| 2 | （徽章行） | ✅ | `<p align="center">` + badge img |
| 3 | （链接行） | ✅ | `<p align="center">` + 链接，` · ` 分隔 |
| 4 | `---` | ✅ | 分隔线 |
| 5 | `## ✨ 为什么做这个{X}` | ✅ | X 填"应用""脚本""项目"等 |
| 6 | `## 📸 截图预览` | 可选 | 无可省略 |
| 7 | `## 🚀 核心能力` | ✅ | 功能特性列表 |
| 8 | `## ⚡ 快速开始` | ✅ | 环境要求 + 安装命令 |
| 9 | `## 📖 使用说明` | ✅ | 用户功能指南 |
| 10 | `## 🧠 功能细节` | ✅ | 设计决策、实现细节 |
| 11 | `## 🧱 技术栈` | ✅ | 语言/框架/平台 |
| 12 | `## 🗂️ 项目结构` | ✅ | tree 格式目录 |
| 13 | `## 👨‍💻 本地开发` | ✅ | 开发命令与质量检查 |
| 14 | `## 🔐 安全报告` | ✅ | SECURITY.md 引用段落 |
| 15 | `## 📄 许可证` | ✅ | LICENSE 引用段落 |
| 16 | `## ⭐ 星标历史` | ✅ | Star History 图表 |
| 17 | 底部 `<div>` 签名 | ✅ | `Built with ❤️ by Sunny` |

### README 正像模板（复制后替换占位符）

```html
<div align="center">
  <!-- <img src="{logo地址}" alt="{项目名} Logo" width="120" /> -->
  <h1>{项目名}</h1>
  <p>{一句话价值概述：15-40字完整句子，说明提供什么功能或解决什么问题}</p>
</div>

<p align="center">
  <img src="https://img.shields.io/github/v/tag/{用户}/{仓库}?label=Release&color=3b82f6" alt="Release" />
  <img src="https://img.shields.io/github/license/{用户}/{仓库}?color=10b981" alt="License" />
</p>
<p align="center">
  <a href="{链接URL}">{链接文本}</a> · <a href="{链接URL}">{链接文本}</a>
</p>

---

## ✨ 为什么做这个{项目类型}

{阐述痛点与核心动机}

## 📸 截图预览

{界面、运行或配置图片预览；无可省略此节}

## 🚀 核心能力

- {功能特性与核心卖点，用无序列表}

## ⚡ 快速开始

### 前置要求

- {运行环境要求}

### 安装与运行

```bash
{可直接复制执行的原生命令}
```

## 📖 使用说明

{用户核心功能指南，含代码示例}

## 🧠 功能细节

{脚本结构、技术实现或本地优先设计等细节}

## 🧱 技术栈

- {语言}：{版本或说明}
- {框架或工具}
- 目标平台：{平台}

## 🗂️ 项目结构

```
{项目名}/
├── {目录或文件}    # {说明}
└── {目录或文件}    # {说明}
```

## 👨‍💻 本地开发

### 环境

{开发环境要求}

### 命令

```bash
{测试命令，可直接执行}
{构建命令，可直接执行}
```

## 🔐 安全报告

如果发现安全问题，请不要公开披露细节。请优先参考仓库中的 [SECURITY.md](./SECURITY.md) 提交安全报告。

## 📄 许可证

本项目基于 [GPL-3.0](./LICENSE) 开源。

## ⭐ 星标历史

[![Star History Chart](https://api.star-history.com/svg?repos={用户}/{仓库})](https://star-history.com/#{用户}/{仓库})

<div align="center">
  <sub>Built with ❤️ by Sunny</sub>
</div>
```

## SECURITY.md

联系方式固定为 `mail@sunnyhmz.top`。每个仓库直接复制 `templates/SECURITY.md`，**不做任何修改**。

## Issue 模板

从 ServerHarbor 复制。应用到具体项目时，将模板中所有 `ServerHarbor` 引用替换为实际项目名。

### 文件

| 文件 | 用途 |
|------|------|
| `templates/config.yml` | 禁用空白 Issue |
| `templates/bug_report.yml` | 缺陷反馈（中英双语，含前置检查清单） |
| `templates/feature_request.yml` | 功能建议（中英双语，含前置检查清单） |

## LICENSE

默认 GPL-3.0。如用户无特殊要求，直接使用标准 GPL-3.0 全文。

## 工作流

新仓库初始化时按以下顺序执行：

1. **分析项目**：读取项目结构、语言、框架、功能定位
2. **填写 README 模板**：将分析结果填入 README 正像模板的占位符
3. **复制固定文件**：SECURITY.md（原样）、Issue 模板（替换项目名）、LICENSE（GPL-3.0）
4. **展示结果**：列出生成的所有文件和关键占位符替换，**等待用户确认后写入**

检查现有 README 时：
1. 对照强制约束逐项检查
2. 列出所有违规项和修复建议
3. 等待用户确认后修改

## Common Mistakes

| 违规表现 | 根因 | 正确做法 |
|---------|------|---------|
| `# 项目名` Markdown 标题代替 `<h1>` | AI 倾向 Markdown 短语法 | 必须用 `<div align="center"><h1>{项目名}</h1></div>` |
| `<p>` 标签缺 `align="center"` | 习惯省略默认属性 | 徽章和链接的 `<p>` 必须写 `<p align="center">` |
| `\[链接\](URL)` 转义了方括号 | Markdown 渲染器误处理 | 标准 `[链接](URL)`，无需转义 |
| `<p>` 内用 `·` 分隔关键词 | 把"一句话"理解成 tagline | 写 15-40 字自然语言完整句子 |
| 标题缺 Emoji 前缀 | 当成普通文档处理 | 每个二级标题按固定顺序带 Emoji |
| 代码块含 `rtk` 命令 | 从聊天上下文带入 | 移除 `rtk`，给可直接执行的命令 |
| 缺 `Built with ❤️ by Sunny` | 忘记底部签名 | 模板底部固定保留 |
| 修改 SECURITY.md 联系方式 | 想个性化 | `mail@sunnyhmz.top` 全局不变 |
| 章节顺序错乱或跳过 | 自由发挥 | 严格按章节顺序表，可选节可跳过其余必须存在 |
| 星标历史图表用了旧格式 | 记错 API 地址 | 固定用 `https://api.star-history.com/svg?repos=` |
