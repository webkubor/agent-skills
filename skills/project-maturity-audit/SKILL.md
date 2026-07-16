---
name: project-maturity-audit
description: 项目成熟度体检 — 按成熟开源项目的标准，从门面、分发、发布工程、质量护栏、社区卫生、文档、安全、度量八个维度对一个仓库做证据化评估打分，输出记分卡和按 ROI 排序的整改清单。触发词：项目体检、成熟度评估、为什么没 star、开源检查、maturity audit、审查我的项目/仓库。可传仓库路径或 GitHub 仓库名作为参数；不传则审查当前目录。
---
# ── 质量追踪 ──
{
  "status": "production",
  "rating": "★★★★★",
  "last_used": "2026-07-16",
  "total_uses": 1,
  "trace": [
    {"date": "2026-07-16", "usage": "收录 agent-skills", "result": "✅ 已投产使用"}
  ]
}

# 项目成熟度体检 (Project Maturity Audit)

按成熟开源项目的标准给仓库做全面体检。**核心纪律：每一条结论都必须有证据（命令输出、文件内容、链接状态码），禁止泛泛而谈。** 评估之后先给报告，用户同意后才动手修。

## 评估流程

### 0. 确定对象与对标

- 对象：参数指定的路径 / GitHub 仓库；缺省用当前目录（`git remote get-url origin` 拿到仓库名）。
- **对标**：用 `gh api "search/repositories?q=<品类关键词>&sort=stars"` 找同品类 star 前 3 的仓库，作为"成熟"的参照系。所有打分都相对同品类头部，而不是抽象标准。

### 1. 八维度检查（并行收集证据）

**① 门面 First Impression（权重高——决定 10 秒去留）**
- README：首屏 10 秒内能否明白"这是什么、给谁用、值不值得装"？有没有 GIF/截图演示？英文在前吗（纯中文 = 放弃全球 80% 受众）？安装能否 30 秒跑通？
- `gh api repos/<r> --jq '{description, topics, homepage}'`：description 是否一句话卖点；topics 是否填满（≥6 个精准词）；homepage 是否配置。
- 徽章：npm 版本/下载量、CI 状态、license——有没有、是不是活的。

**② 分发 Distribution（没 star 的第一嫌疑人）**
- 是否发布到对应 registry（npm/PyPI/crates/…）？`npm view <pkg> version`。
- 是否进入生态收录渠道：awesome-* 列表、官方 gallery/marketplace、插件市场。搜 `gh api "search/code?q=<repo-name>+repo:<awesome-repo>"` 验证。
- 有没有可考的发布动作：HN/Reddit/V2EX/掘金/Twitter 首发帖。
- `gh api repos/<r>/traffic/popular/referrers`（需 push 权限）：流量从哪来？没有外部 referrer = 没有渠道。

**③ 发布工程 Release Engineering**
- 版本化：tag 规范、CHANGELOG 是否持续更新。
- **发布产物完整性**：最新 Release 有没有该有的资产（`gh release view --json assets`）？直链（`releases/latest/download/...`）是否 200？
- 发布管线是否真的在跑：`gh run list` 最近状态；注意 **GITHUB_TOKEN 创建的 tag 不会触发其他 workflow** 这类静默断裂。
- 仓库里提交的产物（zip/dist）与源码是否同步。

**④ 质量护栏 Quality Gates**
- 测试存在且在 CI 跑？lint/typecheck 有没有、挂没挂 pre-commit/CI？
- 领域特定校验（如主题项目的对比度断言、插件项目的多版本兼容矩阵）。
- `git log --oneline -20`：提交信息是否规范（conventional commits）。

**⑤ 社区卫生 Community Hygiene（"被遗忘感"是口碑杀手）**
- LICENSE / CONTRIBUTING / issue 模板齐不齐。
- **open issue 的年龄和响应**：`gh issue list --state open --json createdAt,comments`——超过 30 天无维护者回应的 issue 数量。用户来报 bug 没人理，比没有用户更伤。
- 最近 90 天有没有提交（活跃度信号）。

**⑥ 文档 Docs**
- 安装/快速开始/API 参考/故障排查四件套。
- 链接全量体检：`curl -s -o /dev/null -w "%{http_code}"` 检查 README 和 registry 页里的每个外链——**死链是成熟度的硬伤**（尤其 homepage）。
- 现代加分项：agent 可读文档（AGENT.md/SKILL.md/llms.txt）。

**⑦ 安全 Security**
- 明文密钥扫描：`git log -p | grep -iE "api[_-]?key|secret|token" | head`（抽样即可）。
- 依赖审计：`npm audit --omit=dev` / 等价物。
- SECURITY.md 有无。

**⑧ 度量 Metrics**
- 有没有任何形式的使用数据：网站埋点、下载量追踪、投票/反馈渠道。没有度量 = 无法迭代选品。

### 2. 输出报告

先给一段**直话诊断**（一两句，说清最大的问题是什么），然后：

**记分卡**（每维 0-10 分，必须附证据）：

| 维度 | 得分 | 关键证据 | 最值得做的一件事 |
|---|---|---|---|

**整改清单**：按 `影响 ÷ 成本` 排序的 3-7 条行动，每条标注预估耗时。渠道类动作（提 awesome-* PR、更新 gallery 条目、补 registry 发布）通常 ROI 最高，排前面。

**对标差距**：与同品类头部仓库最刺眼的 1-2 个差距。

### 3. 修复（需用户确认）

报告后询问是否执行整改。执行时遵守：低风险文档/元数据类直接做；外发动作（向第三方仓库提 PR、发社区帖）逐项确认；一切改动过一遍该项目自己的构建/校验。

## 评分基准（校准用）

- 9-10：同品类头部水准（有渠道、有度量、发布全自动、issue 响应 < 7 天）
- 6-8：工程健康但分发薄弱（典型的"好代码没人看"）
- 3-5：能用但门面/发布有明显欠账（死链、断管线、纯单语 README）
- 0-2：个人练习仓库状态

## 已知教训库（评估时对照）

- 发布管线静默断裂：release-please 用 GITHUB_TOKEN 打 tag → 旧的 tag 触发式打包 workflow 永不再跑 → Release 无资产、官网下载按钮 404。
- 收录条目过期：官方 gallery/awesome 列表里的 homepage 死链、功能描述停留在几个版本前——收录渠道是资产，需要随大版本回访维护。
- open issue 积压 = "项目已死"的错觉，即使代码在活跃更新。
- 纯中文 README 直接把 npm/GitHub 全球流量拒之门外；反之纯英文对国内渠道（掘金/V2EX）同理。
