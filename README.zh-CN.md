<div align="center">

# Agent Skills

**[English](./README.md)** | 简体中文

**生产环境验证过的、工具中立的 AI Agent 技能库。**

不是 prompt 片段，也不是某个工具的专属配置。每个 skill 都是一份自包含的"能力文档"——在真实生产工作中打磨出来——任何能读 markdown 指令的 agent 都能挂载：Claude Code、Codex、Gemini CLI、Cursor，或你自己的 harness。

</div>

## 为什么做这个库

Agent 缺的不是智力，是**流程**：怎么亲眼验收一次 UI 改动、怎么不靠猜地调试一个运行中的应用、怎么拦住一次带着泄露密钥的提交。一个 skill 把一条这样的流程写到足够精确——agent 能执行，人能审计。

三条设计原则：

1. **工具中立**。skill 正文永远不假设某个具体的 agent 产品；挂载方式、CLI 差异只出现在安装文档里。
2. **生产验证**。每个 skill 都提炼自每天的真实工作——那些只有实践才踩得到的坑（代理劫持、登录墙、缓存假象、静默断裂的发布管线）都写在里面。
3. **证据优先**。skill 强制验证步骤：截了图必须*读图*再下结论；做了审计必须*引用*命令输出。

## 技能清单

| Skill | 给 agent 的能力 | 配套工具 |
|---|---|---|
| [**agent-eyes**](./skills/agent-eyes) | Vite 应用的运行时视野：读结构化 API/错误/控制台/交互日志、脱敏登录态、截图与 DOM 快照——不猜代码直接诊断，修完自己验证 | [`vite-plugin-agent-eyes`](https://github.com/webkubor/vite-plugin-agent-eyes)（npm）|
| [**browser-verify**](./skills/browser-verify) | 视觉验收（DoD）：CDP 直控真实 Chrome，截图、读页面值、点击、查明暗/移动端——纯 CLI，跨 agent | [`browser-harness`](https://www.npmjs.com/package/browser-harness)（npm）|
| [**clone-website**](./skills/clone-website) | 逐区块逆向重建网站，在隔离 worktree 里并行派发 builder agent | — |
| [**project-maturity-audit**](./skills/project-maturity-audit) | 像资深开源维护者一样体检仓库：八维度证据化评估 + 记分卡 + ROI 排序整改清单，回答"为什么我的项目没 star" | — |
| [**git-worktrees**](./skills/git-worktrees) | 隔离 worktree 开发纪律：每个任务独立 worktree 和分支，完成自动合并清理 | — |
| [**ts-prebuild-check**](./skills/ts-prebuild-check) | TS 项目 diff-only 提交前校验：只检查改动文件，零额外依赖，存量债务不阻塞 | — |

## 快速开始

```bash
git clone https://github.com/webkubor/agent-skills.git
cd agent-skills

# 浏览与筛选（每个技能的 frontmatter 都声明了 category + platform）
./skills-cli list
./skills-cli list --platform xiaohongshu        # 定向：小红书可用技能（含通用）
./skills-cli list --category coding --json      # 机器可读

# 定向导出 — 直接挂载进你的 Agent 运行时
./skills-cli export --platform xiaohongshu --to ~/.claude/skills
./skills-cli export --skills wuxia-cinematic,browser-verify --zip pack.zip

# 按 docs/SKILL-SPEC.md 校验整库
./skills-cli check
```

每次 `export` 会在本地 `delivery-log.jsonl` 追加一条交付记录（时间/技能/去向/操作者，已 git-ignore）。`./skills-cli log` 查看。

只要单个技能、不想 clone：

```bash
npx degit webkubor/agent-skills/skills/wuxia-cinematic ~/.claude/skills/wuxia-cinematic
```

挂载方式见 **[docs/INSTALL.md](./docs/INSTALL.md)**（Claude Code / Codex / Gemini CLI / Cursor / 通用）。最短路径：

- **Claude Code**：把 skill 文件夹拷进 `~/.claude/skills/`（或项目的 `.claude/skills/`）
- **Codex / Gemini CLI / 其他**：在 agent 指令文件（`AGENTS.md`、`GEMINI.md`、system prompt）里引用对应 `SKILL.md`——正文就是纯 markdown 流程

## 理念：skill 是能力，不是配置

一个 skill 应该活得比写它时用的工具久。跨 agent 产品不变的是*流程本身*：何时触发、收集什么证据、"完成"的标准是什么、什么事绝对不能做（比如永远不从截图里读密码）。这就是这些文件编码的东西。哪天 agent 改读 YAML 了，流程照样迁移，配置就没这个命。

## 完整工具链

这些 skills 是一套更大的 local-first agent 工具链的一层：

- [**vite-plugin-agent-eyes**](https://github.com/webkubor/vite-plugin-agent-eyes) — agent-eyes skill 读取的运行时遥测层
- [**browser-harness**](https://www.npmjs.com/package/browser-harness) — browser-verify 背后的 CDP 浏览器 CLI
- [**keyring**](https://github.com/webkubor/keyring) — 密钥存一次，agent 永远看不到明文（AES-256-GCM）；skill 需要凭证时的缺失拼图
- [**voice-editor**](https://github.com/webkubor/voice-editor) — 本地中文 TTS 工作台，带 agent 可调用接口（Qwen3-TTS）
- [**typora-Bloom-theme**](https://github.com/webkubor/typora-Bloom-theme) — project-maturity-audit 教训的来源现场
- 更多分享在 [webkubor.online](https://webkubor.online)

## License

[MIT](./LICENSE)

如果某个 skill 帮你省下了一次调试，点个 ⭐ 让更多人找到它。
