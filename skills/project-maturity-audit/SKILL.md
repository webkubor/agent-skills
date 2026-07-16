---
name: project-maturity-audit
description: 项目成熟度体检 — 自动识别项目类型（Skills/前端/CLI/后端/库/组件），按类型差异化标准从门面、分发、发布工程、质量护栏、社区卫生、文档、安全、度量八个维度做证据化评估打分，输出记分卡和整改清单。触发词：项目体检、成熟度评估、为什么没 star、开源检查、maturity audit、审查我的项目/仓库。可传仓库路径或 GitHub 仓库名作为参数；不传则审查当前目录。
---

# 项目成熟度体检 (Project Maturity Audit)

按成熟开源项目的标准给仓库做全面体检。**核心纪律：每一条结论都必须有证据（命令输出、文件内容、链接状态码），禁止泛泛而谈。** 评估之后先给报告，用户同意后才动手修。

## 评估流程

### 0. 确定对象与类型

- 对象：参数指定的路径 / GitHub 仓库；缺省用当前目录。
- **自动识别项目类型**（检查优先级：package.json > pyproject.toml > Cargo.toml > 单一 SKILL.md > README 中的关键词）：

| 类型 | 识别特征 | 示例 |
|------|---------|------|
| **skill/agent-skill** | 根目录有 SKILL.md 或 `skills/` 目录 | agent-skills, keyring |
| **前端应用** | package.json + vue/react/svelte 依赖，有 build 脚本 | wechat-chat-gen, html-preview |
| **CLI/本地工具** | package.json bin 字段 或 setup.py console_scripts | keyring CLI, voice-editor |
| **库/SDK** | package.json 无 bin，有 exports/main 字段 | vite-plugin-agent-eyes |
| **后端服务** | Dockerfile / docker-compose / 服务端框架（express/fastapi/gin） | — |
| **纯文档/教程** | 只有 markdown，无代码 | xiaobai-kanban |
| **主题/样式** | CSS/SCSS 为主，无 JS 逻辑 | typora-Bloom-theme |

- **对标**：`gh api "search/repositories?q=<品类关键词>&sort=stars"` 找同品类 star 前 3。

### 1. 八维度检查（并行收集证据）

#### ① 门面 First Impression（权重高——决定 10 秒去留）

**通用检查：**
- README：首屏 10 秒内能否明白"这是什么、给谁用、值不值得装"？
- `gh api repos/<r> --jq '{description, topics, homepage}'`：description 一句话卖点；topics ≥6 个精准词；homepage 已配置。
- 徽章：CI 状态、license、版本号——有没有、是不是活的。

**Logo / Social Preview 检查（必须实际查文件，不只看 API）：**

⚠️ **Logo 和 Social Preview 是两个不同的东西，不能混为一谈。**

| 维度 | Logo | Social Preview |
|------|------|---------------|
| **用途** | 网站顶部小图标、npm icon、PyPI badge、GitHub 仓库小图标 | 分享链接到 Twitter/微信/飞书时显示的封面图 |
| **比例** | 1:1 正方形 | 2:1 横版（1280×640px） |
| **格式** | SVG（透明背景）> PNG | PNG/JPG |
| **位置** | README 顶部 `![logo](url)` | GitHub Settings → Social preview，或 README 首张横版图 |
| **背景** | 透明/半透明 | 可有背景色 |

**Logo 检查：**
1. 查仓库文件结构：`gh api repos/<r>/contents` 找 logo.* / icon.* / public/logo.* / assets/logo.*
2. 查 README 是否引用了图片：`gh api repos/<r>/readme --jq '.content' | base64 -d | grep -c '!\['`
3. 查 public/ 目录：favicon.ico、pwa-*.png、logo.svg
4. **SSoT 原则**：一个项目只能有一个官方 logo。多个 logo 文件 = 品牌混乱。
5. **1:1 比例**：logo 必须是正方形（1:1），SVG 透明背景优先。
6. **主题色一致**：logo 颜色必须与项目品牌色/主题色统一。

**Social Preview 检查：**
1. GitHub 会自动从 README 第一张横版图生成 Social Preview。
2. 如果 README 顶部是 1:1 logo（不是横版图），GitHub 会自动裁剪/缩放，效果可能不理想。
3. 最佳实践：README 顶部放 1:1 logo（显示用），同时确保仓库里有一张 2:1 横版图（1280×640）作为 Social Preview 源。
4. `curl -sL "https://github.com/<r>" | grep -o 'og:image.*content="[^"]*"'` 可以检查当前 Social Preview 是否已生效。
5. Social Preview 图应该包含：项目名 + 一句话定位 + 品牌色背景，横版构图。

**类型特有检查：**

| 类型 | 门面重点 |
|------|---------|
| **skill** | SKILL.md 格式规范、prompt 示例可复制、参考图（sample-output.*）存在且清晰 |
| **前端** | 首页有 Live demo 截图/GIF、浏览器兼容列表、移动端适配说明 |
| **CLI** | 安装命令一行跑通、帮助输出截图、跨平台（macOS/Linux/Windows）说明 |
| **库/SDK** | 30 秒 Quick Start 代码块、API 概览表、TypeScript 类型提示 |
| **后端** | API 文档链接、架构图、环境变量列表 |
| **纯文档** | 目录清晰、有学习路径、术语表 |

#### ② 分发 Distribution

- 是否发布到 registry（npm/PyPI/crates/…）？`npm view <pkg> version` / `pip index versions <pkg>`。
- 生态收录：awesome-* 列表、官方 gallery/marketplace。搜 `gh api "search/code?q=<repo-name>+repo:<awesome-repo>"` 验证。
- 发布动作：HN/Reddit/V2EX/掘金/Twitter 首发帖。
- 流量来源：`gh api repos/<r>/traffic/popular/referrers`（需 push 权限）。

**类型特有分发：**

| 类型 | 核心渠道 |
|------|---------|
| **skill** | agent-skills 仓库收录、awesome-agent-skills、Agent 市场 |
| **前端** | Vercel/CF Pages demo、npm/Vue/React 生态 |
| **CLI** | npm/PyPI、Homebrew formula、AUR |
| **库/SDK** | npm/PyPI、官方文档站、包管理器搜索 |
| **后端** | Docker Hub、云市场（AWS/GCP/Azure） |

#### ③ 发布工程 Release Engineering

- 版本化：tag 规范（semver）、CHANGELOG 持续更新。
- Release 资产完整性：`gh release view --json assets` 直链是否 200。
- CI 管线状态：`gh run list` 最近是否通过。
- 产物与源码同步：仓库里不提交 dist/build 产物。

#### ④ 质量护栏 Quality Gates

- 测试存在且 CI 跑。
- lint/typecheck 有无、挂没挂 pre-commit/CI。
- 提交信息规范（conventional commits）。
- **类型特有**：

| 类型 | 质量门 |
|------|--------|
| **skill** | prompt 可复现（同一输入稳定输出）、示例图片清晰无水印 |
| **前端** | Lighthouse 分数、无障碍（a11y）检查、bundle 大小 |
| **CLI** | 卸载干净（无残留文件）、退出码规范、错误信息友好 |
| **库/SDK** | API 兼容性矩阵、breaking changes 策略 |

#### ⑤ 社区卫生 Community Hygiene

- LICENSE / CONTRIBUTING / issue 模板齐不齐。
- Open issue 年龄和响应：`gh issue list --state open --json createdAt,comments`——超 30 天无回应 = 口碑杀手。
- 最近 90 天有提交（活跃度信号）。

#### ⑥ 文档 Docs

- 安装/快速开始/API 参考/故障排查四件套。
- 链接全量体检：`curl -s -o /dev/null -w "%{http_code}"` 检查死链。
- agent 可读文档（AGENT.md/SKILL.md/llms.txt）是加分项。

**类型特有文档：**

| 类型 | 必须有的文档 |
|------|------------|
| **skill** | SKILL.md（含触发词、示例、参数说明）、参考图 |
| **前端** | Demo 链接、截图、部署说明 |
| **CLI** | man page / --help 输出、shell completion、配置文件说明 |
| **库/SDK** | API Reference、Migration Guide、版本策略 |
| **后端** | API 文档（OpenAPI/Swagger）、部署指南、环境变量说明 |

#### ⑦ 安全 Security

- 明文密钥扫描：`git log -p | grep -iE "api[_-]?key|secret|token" | head`。
- 依赖审计：`npm audit --omit=dev` / 等价物。
- SECURITY.md 有无。

#### ⑧ 度量 Metrics

- 使用数据：下载量、网站埋点、反馈渠道。没有度量 = 无法迭代。

### 2. 输出报告

先给**直话诊断**（一两句），然后：

**记分卡**（每维 0-10 分，附证据）：

| 维度 | 得分 | 关键证据 | 最值得做的一件事 |
|---|---|---|---|

**整改清单**：按 `影响 ÷ 成本` 排序，每条标注预估耗时。

**对标差距**：与同品类头部 1-2 个刺眼差距。

### 3. 修复（需用户确认）

报告后询问是否执行。低风险文档/元数据类直接做；外发动作逐项确认。

## 评分基准

- 9-10：同品类头部（有渠道、有度量、发布全自动、issue 响应 < 7 天）
- 6-8：工程健康但分发薄弱（"好代码没人看"）
- 3-5：能用但门面/发布有欠账
- 0-2：个人练习仓库

## 已知教训

- 发布管线静默断裂：GITHUB_TOKEN 打 tag → 旧 workflow 永不再跑 → Release 无资产。
- 收录条目过期：awesome 列表里的 homepage 死链。
- open issue 积压 = "项目已死"错觉，即使代码活跃。
- **Logo 检查不能只看 API 字段**：必须查仓库文件结构（`public/logo.*`、`assets/logo.*`）和 README 引用。API 的 `social_preview_image` 字段不可靠。
- **Logo ≠ Social Preview**：Logo 是 1:1 小图标（网站/npm），Social Preview 是 2:1 横版图（1280×640，分享链接用）。两者用途、比例、格式完全不同。
- **一个项目一个 logo（SSoT）**：多个 logo 文件 = 品牌混乱。
- **Logo 必须 1:1 正方形，SVG 透明背景优先**：适配 npm icon、PyPI badge、GitHub 仓库图标。
- **Social Preview 自动从 README 生成**：GitHub 会抓 README 里第一张横版图作为 Social Preview。如果 README 只有 1:1 logo，GitHub 会裁剪，效果可能不理想。最佳实践是同时准备 logo（1:1）和 social preview（2:1）两张图。
