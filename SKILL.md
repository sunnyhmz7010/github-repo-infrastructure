---
name: github-repo-infrastructure
description: Create or update GitHub repository infrastructure, including README, SECURITY.md, issue templates, LICENSE, and GitHub Actions CI/CD workflows. Use for repository initialization, project documentation, workflow setup, or checking these files against the repository conventions.
---

# GitHub 仓库基础设施

## Overview

一站式 GitHub 仓库基础设施：面向使用者的 README、SECURITY.md 安全策略、Issue 模板、GPL-3.0 许可证与 GitHub Actions CI/CD 工作流。仓库中需要复用的固定文件和工作流基础模板均已存放在 `templates/` 目录。执行任务时应优先复制模板，而不是重新生成固定内容或从外部仓库获取文件。

## When to Use

- 新建 GitHub 仓库时初始化基础设施文件（README、SECURITY.md、ISSUE_TEMPLATE、LICENSE）
- 用户要求"生成 README""写项目文档""添加安全策略""设置 Issue 模板"
- 补全仓库的 Issue 模板、PR 模板或社区健康文件
- 检查现有 README 是否符合规范骨架并修复
- 创建、补全或检查 GitHub Actions 的 CI 验证与 Release 产物发布工作流

## README 规范（面向使用者）

默认面向第一次接触项目的小白使用者，用简体中文帮助读者看懂用途、找到下载入口并完成第一次使用。写作前核对实际功能、发布文件、运行要求和界面名称；以项目源码与现有发布产物为依据。

### 内容与语言

- **为什么做这个应用**：第一段只写背景和痛点，后面用圆点列出具体使用场景；直接写什么时候用、解决什么问题，不写“XX 是一款”等应用定义，不在这里重复功能清单
- **核心能力**：用圆点列表介绍用户能理解的动作和效果，不添加子标题；避免框架名、接口路径和实现机制堆叠
- **快速开始**：优先给出推荐的使用路线；项目实际支持多种安装或部署方式时，在“📦 安装与运行”下用三级标题分别说明，写清必要配置、启动、访问方式和成功结果；部署必需的镜像构建属于该安装路线，开发、测试和发版流程放到本地开发
- **使用方式**：围绕实际任务分组，用步骤说明点击哪里、输入什么、接下来做什么；可选能力与首次使用分开介绍，术语首次出现时作简短解释
- **功能细节**：允许稍偏开发者，按功能简短说明原理、特点和使用边界；可以提及 JSON、REST API、缓存、加密等技术用语，并交代实际作用，完整接口与代码实现另放开发资料
- **列表标点**：圆点列表条目末尾不加中文或英文句号；普通段落正常使用标点，条目内部可按需要断句
- 文本格式：只保留标题格式自带的粗体效果，正文、列表和表格不使用 Markdown 粗体或 HTML 粗体标签
- **信息分层**：头部技术栈标签和正文“🧱 技术栈”章节都必须保留；正文用简短列表说明实际技术及用途，再用“🗂️ 项目结构”展示主要目录；“👨‍💻 本地开发”固定保留“🧰 环境”和“⚙️ 命令”子章节，直接展示内容，不使用折叠块
- 本地开发环境：使用圆点列表，逐项写明开发平台的系统、版本和架构，以及语言、工具的实际版本要求
- **必要说明**：保留影响用户选择和操作的数据保存、备份、权限及功能限制，放在相关功能附近；内容以实际情况为准，不编造能力、截图、下载入口或尚不存在的文档链接

### 头部与格式

1. **头部使用 HTML**：`<div align="center">` 包含可选 Logo、`<h1>` 项目名和 `<p>` 一句话介绍，顺序不变
2. **一句话介绍**：15–40 字的完整句子，直接说明用途，末尾不加中文或英文句号；不用 `·` 分隔关键词或列举特性
3. **技术栈标签**：在介绍下方单独使用 `<p align="center">`，采用 VoCat 同款 Shields.io `style=flat-square` 样式，使用品牌色，有可用图标时加 `logo`；展示主要语言、框架、数据库等实际技术，版本从配置或锁文件读取，无法确认时仅写名称
4. **项目状态徽章**：在技术栈标签下方另起居中一行，仅按实际情况保留 Release、License、CI 徽章，不额外添加运行平台等徽章；沿用原模板样式，不添加 `style=flat-square`，只有技术栈标签使用 VoCat 样式；没有对应发布、文件或工作流时省略，不虚构状态
5. **章节标题**：正文标题严格遵守下方白名单与层级规则，固定标题不得改名、替换或省略；所有标题前必须有合适的 Emoji，标题前的 Emoji 在整篇 README 中不得重复，没有 Emoji 的文字不得设置为标题
6. **代码块**：标明语言，只保留当前步骤需要的命令、配置或示例代码；命令使用可直接复制的原生命令，不带 `rtk` 前缀，占位值说明如何替换
7. **固定声明与签名**：模板中的安全报告段落、许可证段落和 `Built with ❤️ by Sunny` 必须逐字保留，包括标点、链接文字和完整链接地址；用户指定的 `start-your-python` 链接也不得替换为目标仓库地址，签名保持原有 HTML 换行结构

### 标题层级与章节安排

本规范所称的一级、二级、三级标题分别对应正文的 `##`、`###`、`####`。正文有且仅有下表十个一级标题，文字、Emoji 和顺序固定；不得新增其他一级标题，也不使用第四级及更深层级的标题。

| 顺序 | 一级标题 | 允许的二级标题 | 允许的三级标题 |
|------|----------|----------------|----------------|
| 1 | `## ✨ 为什么做这个应用` | 不允许 | 不允许 |
| 2 | `## 🚀 核心能力` | 不允许 | 不允许 |
| 3 | `## ⚡ 快速开始` | 有且仅有 `### 📋 前置要求`、`### 📦 安装与运行` | 仅“📦 安装与运行”下允许按实际支持的安装或部署方式添加，见下方部署指引 |
| 4 | `## 📖 使用方式` | 可按实际任务设置 | 不允许 |
| 5 | `## 🧠 功能细节` | 可按实际功能设置 | 不允许 |
| 6 | `## 🧱 技术栈` | 不允许 | 不允许 |
| 7 | `## 🗂️ 项目结构` | 不允许 | 不允许 |
| 8 | `## 👨‍💻 本地开发` | 有且仅有 `### 🧰 环境`、`### ⚙️ 命令` | 不允许 |
| 9 | `## 🔐 安全报告` | 不允许 | 不允许 |
| 10 | `## 📄 许可证` | 不允许 | 不允许 |

截图和常见问题不再单独设为一级标题；有相关内容时放入“📖 使用方式”下组织。安全报告段落、许可证段落和末尾签名继续使用模板中的固定原文。

### 安装与运行：Docker 与 Cloudflare 部署指引

只为项目实际支持的部署方式设置三级标题（`####`），全部放在 `### 📦 安装与运行` 下。单一路线可直接写步骤，多条路线先说明各自适合的场景并将推荐方式排在前面；用户选择其中一种即可，不把替代路线写成连续必做步骤。

| 三级标题 | 使用条件 |
|----------|----------|
| `#### 🐳 Docker Compose 部署` | 支持 Docker Compose 时优先使用；推荐标记仅加在当前项目的推荐路线后 |
| `#### 🖥️ Docker 命令行部署` | 按需补充 `docker run`，参数须与实际运行配置一致 |
| `#### 🛠️ 自行构建镜像` | 需要或允许从源码构建镜像时使用 |
| `#### ☁️ Cloudflare 部署` | 已提供实际可用的 Workers 或 Pages 配置时使用 |
| `#### 🔧 首次初始化` | 多条部署路线共用初始化流程、且需要单独说明时使用 |

这些三级标题也必须遵守 Emoji 全篇唯一；与其他可变子标题冲突时选用其他合适的 Emoji，固定一级标题及规定的二级标题不改。三级标题下使用普通段落、列表、表格和代码块，不再添加更深层级标题，也不使用粗体或折叠块。

Docker 部署必须写清：

- 前置要求放在“📋 前置要求”：Docker Engine、使用 Compose 时需要的 Compose 版本，以及该路线实际需要的平台和账号
- Compose 路线写明配置保存为哪个文件，给出可复制的最小完整 YAML；镜像地址与标签、端口映射、必要环境变量和数据卷以对应版本的实际配置为准，说明哪些值需要替换
- 给出启动命令和查看日志的命令，随后写出本机或远程服务器的访问地址，以及看到哪个页面代表启动成功；不能让远程部署者误把自己电脑的 `localhost` 当作服务器
- 说明数据保存在哪个挂载目录或数据卷；预构建镜像需要访问权限时明确说明，无法确认可拉取时不要宣称直接拉取即可使用
- 自行构建路线按实际情况写出获取源码、构建镜像和启动命令；如使用仓库 Compose 文件，构建的镜像名称必须与配置一致

Cloudflare 部署必须写清：

- 前置要求放在“📋 前置要求”：所需 Cloudflare 账号、GitHub 账号及实际需要开通的服务；按仓库配置区分 Workers 与 Pages，不混写部署入口
- 控制台路线写明如何获取仓库副本、连接仓库和选择部署类型；用表格列出需要填写的根目录、构建命令、部署命令或输出目录，值从项目配置和脚本读取，无需填写的项目明确写“留空”
- 列出项目实际需要的环境变量、Secrets 和资源绑定，说明名称、用途、必填或可选、在哪里填写，以及资源是自动创建还是需要手动准备；不能把某个项目自动创建 D1/R2 的行为推广到所有项目
- 公开 Workers 项目具备相应部署配置时，可以在本节放置指向该项目的一键部署按钮：`[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/{用户}/{仓库})`；按钮路线按其引导操作，不额外要求先完成手动 Fork；Pages 项目不套用该 Workers 按钮
- Wrangler 命令行路线按需补充，使用项目实际的依赖安装、登录和部署命令，不一律硬套 `npm run cf:deploy`
- 部署后写明从哪里获取访问 URL、首次打开后如何初始化，以及看到什么代表可用；共同初始化流程可放在“🔧 首次初始化”中，相关地址和步骤不得只写成“自行配置”

部署写法参考：[HashDrop 的 Docker 配置与使用说明](https://github.com/sunnyhmz7010/HashDrop)、[华文知行的 Docker 与 Cloudflare 部署](https://github.com/Ryrant/wenqu-chinese-learning-platform)。核对具体功能时，以目标仓库的 Compose、Dockerfile、Wrangler 配置及实际脚本为准；Cloudflare 平台行为以[官方部署按钮文档](https://developers.cloudflare.com/workers/platform/deploy-buttons/)和[Wrangler 配置文档](https://developers.cloudflare.com/workers/wrangler/configuration/)为准。

层级示例（只保留项目实际支持的路线）：

````markdown
## ⚡ 快速开始

### 📋 前置要求

- {按部署方式分别列出必要条件}

### 📦 安装与运行

#### 🐳 Docker Compose 部署

{配置文件、启动与日志命令、访问地址和数据保存位置}

#### ☁️ Cloudflare 部署

{部署入口、实际构建配置、绑定与变量、访问地址}

#### 🔧 首次初始化

{需要时填写共同的初始化步骤}
````

### README 模板

保留头部样式和十个固定一级章节，仅在上表允许的位置设置子标题。以下安装与运行段为通用占位；需要 Docker 或 Cloudflare 部署时，按上方部署指引替换为实际支持的三级标题及完整步骤，不支持的路线不写。技术版本、分支和工作流根据目标仓库填写，安全报告与许可证段落及其链接地址不属于可替换内容。

````markdown
<div align="center">
  <img src="{真实Logo地址}" alt="{项目名} Logo" width="96" />
  <h1>{项目名}</h1>
  <p>{一句话介绍，末尾不加句号}</p>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/{技术名}-{版本}-{品牌色}?style=flat-square&amp;logo={图标标识}&amp;logoColor=white" alt="{技术名} {版本}" />
</p>

<p align="center">
  <a href="https://github.com/{用户}/{仓库}/releases"><img src="https://img.shields.io/github/v/release/{用户}/{仓库}?label=Release&amp;color=3b82f6" alt="Release" /></a>
  <a href="https://github.com/{用户}/{仓库}/blob/{默认分支}/LICENSE"><img src="https://img.shields.io/github/license/{用户}/{仓库}?color=10b981" alt="License" /></a>
  <a href="https://github.com/{用户}/{仓库}/actions/workflows/{工作流文件}"><img src="https://img.shields.io/github/actions/workflow/status/{用户}/{仓库}/{工作流文件}?branch={默认分支}&amp;label=CI" alt="CI" /></a>
</p>

---

## ✨ 为什么做这个应用

{一段实际背景和痛点}

- {具体使用场景}
- {另一个具体使用场景}

## 🚀 核心能力

- {功能名称}：{用户能完成什么}

## ⚡ 快速开始

### 📋 前置要求

- {用户实际需要的系统、平台或账号；开发依赖另列}

### 📦 安装与运行

1. {打开真实下载入口，选择对应文件；需要部署时提供最小配置和启动命令}
2. {打开或启动应用}
3. {完成第一次操作，并说明预期看到的结果}

## 📖 使用方式

### 📝 {具体任务}

1. {点击哪个入口}
2. {输入或选择什么}
3. {完成后的结果}

## 🧠 功能细节

### 💾 {功能名称}

{用简短文字说明原理、必要技术用语及其实际作用}

## 🧱 技术栈

- {主要技术}：{实际用途}

## 🗂️ 项目结构

```text
{项目名}/
├── {主要目录}/    # {用途}
└── {入口文件}     # {用途}
```

## 👨‍💻 本地开发

### 🧰 环境

- 开发平台：{操作系统、系统版本及架构}
- {语言或工具名称}：{实际版本要求}

### ⚙️ 命令

```bash
{项目实际构建与检查命令}
```

## 🔐 安全报告

如果发现安全问题，请不要公开披露细节。请优先参考仓库中的 [SECURITY.md](https://github.com/sunnyhmz7010/start-your-python/blob/main/SECURITY.md) 提交安全报告。

## 📄 许可证

本项目基于 [GPL-3.0](https://github.com/sunnyhmz7010/start-your-python/blob/main/LICENSE) 开源。

<div align="center">
  <sub>Built with ❤️ by Sunny</sub>
</div>
````

## SECURITY.md

默认联系方式为 `mail@sunnyhmz.top。如用户无特殊要求，直接复制 `templates/SECURITY.md`。

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

本规范固定工作流文件头和 CI/CD 职责边界。`jobs` 内的具体步骤、构建方式、Action 及其版本按项目实际需要选择，不要求与参考工作流或其他项目相同；不得为了套用模板修改正常工作的实现，也不得增加超出职责的流程。

### CI 固定文件头

`.github/workflows/ci.yml` 必须以以下内容开头并原样保留，`name`、`on`、`permissions` 的值及结构不能改动，不得更换分支、增加其他触发入口或权限；项目相关的 `jobs` 写在其后。

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

### CD 固定文件头

`.github/workflows/cd.yml` 必须以以下内容开头并原样保留，`name`、`on`、`permissions` 的值及结构不能改动，不得增加其他触发入口或权限；项目相关的 `jobs` 写在其后。

```yaml
name: CD

on:
  release:
    types:
      - published

permissions:
  contents: write
```

以下三个工作流及本地模板用于参考职责划分和项目实现；除固定文件头外，不要求照搬具体流程或版本。

| 参考标准 | 本地模板 | 适用场景与目标路径 |
|----------|----------|--------------------|
| [Halo 插件 CI](https://github.com/sunnyhmz7010/halo-plugin-schedule-calendar/blob/main/.github/workflows/ci.yml) | [ci-gradle.yml](templates/workflows/ci-gradle.yml) | Gradle + pnpm 项目的构建与测试，复制为 `.github/workflows/ci.yml` |
| [Halo 插件 CD](https://github.com/sunnyhmz7010/halo-plugin-schedule-calendar/blob/main/.github/workflows/cd.yml) | [cd-gradle.yml](templates/workflows/cd-gradle.yml) | 构建插件 JAR 并上传 Release，复制为 `.github/workflows/cd.yml` |
| [Trylet CD](https://github.com/sunnyhmz7010/Trylet/blob/main/.github/workflows/cd.yml) | [cd-windows.yml](templates/workflows/cd-windows.yml) | Go + Node.js 项目的 Windows 双架构发布，复制为 `.github/workflows/cd.yml` |

模板仅用于任务明确要求新建的工作流，不用于覆盖或规范化已有工作流。按项目实际需要选择 CI 或 CD 模板，不要求成对配置，不同时复制两份 CD；其他技术栈沿用下面的职责与发布约定，替换必要的环境设置和构建步骤。

### 职责边界与精简原则

- CI 负责测试、静态分析、代码质量和回归检查；CD 仅负责检出发布代码、准备必要构建环境、构建可分发产物、命名或必要打包，以及上传到对应 Release
- 即使项目没有 CI，CD 也不得承担 CI 职责；不得向 CD 添加 lint、前端测试、Go 测试、`go vet`、覆盖率或体积门禁、独立验证 job，也不得通过调用脚本或其他工作流变相加入这些检查
- 构建本身必需的编译和类型检查属于构建；额外的测试与质量门禁不属于构建。参考插件 CD 使用 `assemble`，不能为“发布前更稳妥”改成会执行测试的 `build` 或 `check`
- 每一步都应直接服务于当前工作流的职责；复用已有构建入口，不重复安装或构建，不增加没有交付需求的产物、artifact 中转或条件分支，不以“补全流程”“最佳实践”为由扩充任务
- 发现缺少 CI 时只说明现状；用户未要求配置 CI，就不自动新建 CI，也不把检查塞进 CD

Trylet 的取舍可见历史提交：[删除 `workflow_dispatch`](https://github.com/sunnyhmz7010/Trylet/commit/bf813a43570045c51f9788acd15a277f6b40bee6)、[移除 CD 中的测试、静态检查及手动构建分支](https://github.com/sunnyhmz7010/Trylet/commit/da056c68e3694c5ace7c5f1dcaebad1f97d22013)。这些已删除的步骤不是待补功能，不得重新引入。

### 已有工作流修改限制

- AI 默认只读已有 `.github/workflows/*`；只有项目发生重大变更，且有实际失败或可验证的不兼容证据表明原有流程已无法正常工作时，才允许做恢复原职责的最小必要修改
- 普通功能开发、文档调整、常规依赖变化、发现更新的 Action 版本或与模板风格不同，都不是修改工作流的理由；不得顺手升级 Action、统一版本或格式、重排步骤、调整权限或重构 job
- 不得擅自添加 `workflow_dispatch`、手动输入参数、额外的 tag 推送、定时或工作流串联触发；也不得为这些入口增加版本回退、临时产物上传等配套分支
- 修改前必须说明项目重大变更、原流程失效的具体证据和必须调整的步骤；修改只覆盖失效部分，保持现有触发条件、职责、权限和产物约定，不能借修复扩大流程
- 仅要求检查、修改 README 或维护其他基础设施时，不改动 Actions；没有足够失效证据就保留原文件

### 文件、触发与职责

- CI 严格使用上方固定文件头，仅在 `main` 分支的 `push` 和以 `main` 为目标的 `pull_request` 上运行，不按项目默认分支擅自替换
- CI 执行项目真实的构建、测试或质量检查，不创建 Release、不上传 Release 附件，不使用 `pull_request_target` 执行外部 PR 代码
- CD 严格使用上方固定文件头，由 Release 的 `published` 事件触发，不额外添加 tag 推送触发或重复创建 Release
- `published` 同时覆盖正式版和预发布版，不擅自添加发布类型过滤或其他触发条件
- CD 检出该 Release 标签对应的代码，不能固定检出 `main`；默认 checkout 可使用 Release 事件提供的标签引用

Release 事件与引用语义见 [GitHub 官方文档](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#release)。

### 权限与凭据

- CI 和 CD 均保留固定文件头中的权限：CI 为 `contents: read`，CD 为 `contents: write`，不增加或覆盖为其他权限
- 发布方式及凭据传递可沿用项目已有实现，不要求采用相同的 Action 或 CLI；参考模板通过仓库自带的 `GITHUB_TOKEN` 上传附件，无需额外配置个人访问令牌
- 使用 GitHub CLI 时，模板以步骤级 `GH_TOKEN`、`GH_REPO` 和 `RELEASE_TAG` 传入令牌、仓库与标签；这些是实现示例，不是必须照搬的步骤结构
- 标签等事件数据通过 `env` 传给脚本，并按 Shell 规则引用；不将事件表达式直接拼入 `run` 命令

环境变量传参方式见 [GitHub 脚本注入防护说明](https://docs.github.com/en/actions/reference/security/secure-use#use-an-intermediate-environment-variable)。

### 环境、缓存与构建

- Action 的选择及版本不作统一要求，只需满足项目构建需要；模板中的版本仅作示例，不能用它要求其他项目升级、降级或统一。已有工作流仍受上方修改限制约束
- 语言、包管理器及相关版本从项目配置、锁文件和构建脚本读取；Temurin Java 21、Node.js 22、pnpm 9.15.9 等均为模板示例，不是固定要求
- 环境准备和缓存按项目实际需要配置，不要求采用相同 Action、Corepack 命令、缓存方案或步骤划分；缓存路径如有配置，必须对应真实依赖文件
- 优先调用项目已有的统一构建入口：参考 CI 使用 `./gradlew build`，插件 CD 使用 `./gradlew -Pversion=... assemble`，Windows CD 使用 `./build.ps1`；不重复安装或构建已由入口完成的步骤
- CI 必须实际执行项目配置的检查；Gradle 没有配置测试时，不能仅凭 `build` 成功声称测试已通过

### 版本与发布产物

- Release 标签作为发布版本来源；Gradle 示例将 `v1.2.3` 去掉开头的 `v` 后写入 `$GITHUB_OUTPUT`，再通过 `-Pversion` 传给构建，不提交临时版本修改
- 上传到触发工作流的 Release，不新建 Release；参考模板使用 `gh release upload "$RELEASE_TAG" <实际产物路径> --clobber`，其他实现只需保持对应的发布职责
- 上传路径必须对应本次构建生成的可分发文件；Gradle 模板使用 `build/libs/*.jar`，适配时排除不应发布的 sources、javadoc、plain 等附属包
- Windows 模板以 `{项目名}-{标签}-windows-{架构}.exe` 演示命名；项目可按实际分发方式命名，产物必须与其声明的平台、架构和版本相符
- 构建失败、产物缺失或上传失败必须使任务失败，不使用 `continue-on-error` 或吞掉退出码的脚本掩盖发布失败

### Windows 多架构发布

- Trylet 模板演示双架构矩阵；矩阵、runner、Shell、超时和任务拆分均为实现示例，按项目实际目标选择，不要求相同
- 模板通过 `BUILD_ARCH` 传递目标架构；使用其他构建方式也必须生成对应架构的二进制，不能只改附件名
- 模板保留 `build.ps1`、`bin/Trylet.exe` 和 `Trylet` 名称作为参考，复制后必须替换为目标项目真实的入口、输出路径和项目名

### 适配与验证

先判断任务是否明确要求新建工作流，或已有工作流是否满足上述修改条件；未满足时只读检查，不按模板重写。允许写入时，再核对默认分支、技术栈、锁文件、构建入口、目标平台和预期产物。检查 YAML、职责边界、必要步骤、事件、权限、矩阵、Shell、版本传递和上传路径，尤其确认 CD 未夹带 CI 检查、未新增触发入口；在本地验证不代表要向工作流添加验证步骤。本地静态校验与 GitHub Actions 实际运行结果分别说明。仅要求编写工作流时，不额外发布 Release 或上传附件。

## 工作流

新仓库初始化时按以下顺序执行：

1. **分析项目**：核对受众、功能、运行要求、发布产物和真实入口，再读取技术配置
2. **编写 README**：按本规范组织背景、使用场景、推荐上手路线和简短功能细节，填写头部标签，严格保留十个一级标题及规定的子标题
3. **复制固定文件**：SECURITY.md（原样）、Issue 模板（替换项目名及其他必要调整的内容）、LICENSE（GPL-3.0）
4. **处理 Actions**：仅在任务明确要求新建 CI/CD 时适配模板，不自动补齐缺失工作流；已有工作流默认只读，仅在项目重大变更导致原流程失效且有具体证据时作最小修复
5. **执行写入**：在用户已授权的范围内直接完成修改和验证；仅要求检查或预览时，不覆盖目标仓库文件
6. **验证结果**：核对标题白名单、父子层级、Emoji 全篇唯一及正文无粗体，再核对下载与操作路径、版本标签、文档链接、代码块和列表标点；涉及 Actions 时追加工作流适配与验证检查

检查现有 README 时：
1. 对照受众、内容规则和头部格式检查，优先判断能否看懂用途并完成首次使用
2. 列出具体问题及修改建议，避免仅凭篇幅或章节数量评判
3. 用户已授权修订时直接修改并验证；仅要求检查时交付检查结果
