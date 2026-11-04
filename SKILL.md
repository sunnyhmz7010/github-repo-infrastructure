---
name: github-repo-infrastructure
description: Create or update GitHub repository infrastructure, including README.md, SECURITY.md, issue templates, LICENSE, and GitHub Actions CI/CD workflows. Use for repository initialization, project documentation, workflow setup, or checking these files against the repository conventions.
---

# GitHub 仓库基础设施

## Overview

一站式 GitHub 仓库基础设施：README.md、SECURITY.md、Issue 模板、许可证与 GitHub Actions CI/CD 工作流。仓库中需要复用的固定文件均已存放在 `templates/` 目录。执行任务时应优先复制模板，而不是重新生成固定内容或从外部仓库获取文件。

## README.md

`templates/README.md`是**可直接填空的 HTML 模板**。除内容有特殊说明外，你只替换 `{占位符}`，不增删改任何 HTML 结构、Emoji 前缀或章节顺序。

README 默认面向第一次接触项目的小白使用者，用简体中文帮助读者看懂用途、找到下载入口并完成第一次使用。写作前核对实际功能、发布文件、运行要求和界面名称；以项目源码与现有发布产物为依据。

### 强制约束

1. **所有二/三/四级标题必须带 Emoji 前缀（含模板内的 H3 子标题，直接沿用模板 Emoji，勿去掉）**，按下方固定顺序排列。**不增删改顺序、章节标题或 Emoji，不跳过非可选章节**
2. **代码块**：标明语言，只保留当前步骤需要的命令、配置或示例代码；命令使用可直接复制的原生命令，不带 `rtk` 前缀，占位值说明如何替换
3.`## 🧱 技术栈` 和 `### 🧰 环境` 下只允许使用无序列表（`- `），必要说明写入对应列表项；不得在列表前后添加独立段落、表格或其他非列表内容。
4.`## 👨‍💻 本地开发` 采用极简的“环境列表 + 任务命令”结构：`### 🧰 环境` 位于本节开头，其余标题按实际需要设置，例如 `### 🔨 构建插件`、`### 🎨 前端开发`。`### ⚙️ 命令` 为可选标题；模板中的操作小节允许改名、增删，不限制为固定两个标题。以可直接执行的命令代码块为主，代码块内可用简短注释说明命令用途；仅在必要时简短标明产物位置或运行入口，不添加 CI/CD 检查、构建、发布或产物下载流程，也不展开脚本行为和依赖获取过程。

### 标题层级与章节安排

本规范所称的一级、二级、三级标题分别对应正文的 `##`、`###`、`####`。正文一级标题仅限下表十个必需章节和一个可选的“📸 截图预览”，文字、Emoji 和相对顺序固定；不得新增其他一级标题，也不使用第四级及更深层级的标题。

| 顺序 | 一级标题 | 允许的二级标题 | 允许的三级标题 |
|------|----------|----------------|----------------|
| 1 | `## ✨ 为什么做这个{X}`（X 填"应用""脚本""项目"等） | 不允许 | 不允许 |
| 2 | `## 📸 截图预览`（可选） | 不允许 | 不允许 |
| 3 | `## 🚀 核心能力` | 不允许 | 不允许 |
| 4 | `## ⚡ 快速开始` | 有且仅有 `### 📋 前置要求`、`### 📦 安装与运行` | 仅“📦 安装与运行”下允许按实际支持的安装或部署方式添加，见下方部署指引 |
| 5 | `## 📖 使用说明` | 可按实际任务设置 | 不允许 |
| 6 | `## 🧠 功能细节` | 可按实际功能设置 | 不允许 |
| 7 | `## 🧱 技术栈` | 不允许 | 不允许 |
| 8 | `## 🗂️ 项目结构` | 不允许 | 不允许 |
| 9 | `## 👨‍💻 本地开发` | 必须包含 `### 🧰 环境` 且位于开头；其余可按实际开发任务设置，标题须以 Emoji 开头 | 不允许 |
| 10 | `## 🔐 安全报告` | 不允许 | 不允许 |
| 11 | `## 📄 许可证` | 不允许 | 不允许 |

## SECURITY.md

默认联系方式为 `mail@sunnyhmz.top`。如用户无特殊要求，直接复制 `templates/SECURITY.md`。

## Issue 模板

Issue 模板均从 `templates/` 目录复制。

### 文件

| 文件 | 用途 |
|------|------|
| `templates/config.yml` | 禁用空白 Issue |
| `templates/bug_report.yml` | 中英双语缺陷反馈模板 |
| `templates/feature_request.yml` | 中英双语功能建议模板 |

Issue 模板应以 `templates/` 中的文件为基础，但允许根据项目实际情况调整字段内容。

### 允许调整的内容

可以根据项目的语言、框架、运行方式和部署环境修改：

- 字段的 `label`
- 字段的 `description`
- 字段的 `placeholder`
- 与项目版本、运行环境、依赖、部署方式相关的提示文本
- 不适用于当前项目的环境示例
- 项目名称占位符或旧项目名引用
- 为准确收集问题信息而新增、删除或调整的项目特定字段

例如：

- Python 项目可要求填写 Python、pip/uv/poetry 版本
- Node.js 项目可要求填写 Node.js、npm/pnpm/yarn 版本
- Docker 项目可要求填写 Docker、Compose、镜像标签和宿主机环境
- 前端项目可要求填写浏览器、操作系统和构建工具版本
- CLI 工具可要求填写命令、参数、终端和 Shell 环境
- 服务端项目可要求填写部署方式、数据库、中间件和日志信息

### 默认保留的内容

除非项目实际需求不适用，否则应保留：

- Issue Form 的 YAML 基本结构和合法语法
- 中英双语风格
- 必要的前置检查清单
- 问题复现步骤
- 预期行为与实际行为
- 日志、截图或补充信息字段
- 通用的提交质量要求

模板不是不可修改的固定成品，而是项目适配的基础骨架。修改时应以提高问题信息质量为目标，不得机械保留与项目无关的字段或示例。

如果模板内容已经完全适合当前项目，则直接复制，仅替换项目名等变量。

## LICENSE

默认 GPL-3.0。如用户无特殊要求，直接使用标准 GPL-3.0 全文。

## GitHub Actions 工作流规范

本规范固定工作流文件头和 CI/CD 职责边界。`jobs` 内的具体步骤、构建方式、Action 及其版本按项目实际需要选择；不得为了套用模板修改正常工作的实现，也不得增加超出职责的流程。按项目实际需要选择 CI 或 CD 模板，不要求成对配置，不同时复制两份 CD。默认只读已有 `.github/workflows/*`；只有项目发生重大变更，且有实际失败或可验证的不兼容证据表明原有流程已无法正常工作时，才允许做恢复原职责的最小必要修改。不得擅自添加触发条件。

### CI 固定文件头

`.github/workflows/ci.yml` 必须以以下内容开头并原样保留，`name`、`on`、`permissions` 的值及结构不得改动；项目 `jobs` 写在其后。

```yaml
name: CI

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

permissions:
  contents: read
```

CI 负责测试、静态分析、代码质量和回归检查；不创建 Release、不上传 Release 附件，不使用 `pull_request_target` 执行外部 PR 代码。

### CD 固定文件头

`.github/workflows/cd.yml` 必须以以下内容开头并原样保留，`name`、`on`、`permissions` 的值及结构不得改动；项目 `jobs` 写在其后。

```yaml
name: CD

on:
  release:
    types:
      - published

permissions:
  contents: write
```

CD 仅负责检出 Release 标签代码、准备构建环境、构建可分发产物、命名或必要打包、上传到对应 Release。不得承担 CI 职责：不得添加 lint、前端测试、Go 测试、`go vet`、覆盖率或体积门禁、独立验证 job，也不得通过脚本或其他工作流变相加入这些检查。Release 标签作为发布版本来源，上传到触发工作流的 Release，不新建 Release；产物命名须体现平台、架构和版本。
