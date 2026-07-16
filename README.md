![logo](https://cdn.jsdelivr.net/gh/webkubor/picx-images-hosting@master/blog/projects/agent-skills/cs-token4ai-1784193630762882000.png)

<div align="center">

# Agent Skills

English | **[简体中文](./README.zh-CN.md)**

**Production-tested, tool-agnostic skills for AI coding agents.**

Not prompt snippets. Not one tool's config format. Each skill is a self-contained capability document — battle-tested in real production work — that any agent able to read markdown instructions can mount: Claude Code, Codex, Gemini CLI, Cursor, or your own harness.

| [![skills](https://img.shields.io/badge/skills-43-6366f1)](./skills)
[![format](https://img.shields.io/badge/format-SKILL.md-10b981)](https://agentskills.io)
[![license](https://img.shields.io/badge/license-MIT-green)](./LICENSE)

</div>

## Why this exists

Agents don't lack intelligence — they lack **procedures**: how to verify a UI change with their own eyes, how to debug a running app without guessing, how to keep a commit from shipping a leaked secret. A skill encodes one such procedure precisely enough that an agent can execute it and a human can audit it.

Design principles:

1. **Tool-agnostic.** The skill body never assumes a specific agent product. Runtime-specific bits (how to mount, which CLI) live only in the install docs.
2. **Production-tested.** Every skill here is extracted from daily real-world use — the sharp edges you only find in practice (proxy hijacking, login walls, stale bundles, half-broken release pipelines) are written in.
3. **Evidence over vibes.** Skills demand verification steps: screenshot then *read* the screenshot; audit then *cite* the command output.

## The skills

### Coding agent skills

| Skill | What it gives an agent | Companion tooling |
|---|---|---|
| [**agent-eyes**](./skills/agent-eyes) | Runtime vision for Vite apps: read structured API/error/console/interaction logs, screenshots and DOM snapshots — debug without guessing | [`vite-plugin-agent-eyes`](https://github.com/webkubor/vite-plugin-agent-eyes) |
| [**browser-verify**](./skills/browser-verify) | Visual definition-of-done: drive Chrome via CDP, screenshot, read values, click, check light/dark/mobile | [`browser-harness`](https://www.npmjs.com/package/browser-harness) |
| [**clone-website**](./skills/clone-website) | Reverse-engineer and rebuild websites, dispatching parallel builder agents in isolated worktrees | — |
| [**project-maturity-audit**](./skills/project-maturity-audit) | 8-dimension evidence-based repo audit: scorecard + ROI-sorted fixes | — |
| [**git-worktrees**](./skills/git-worktrees) | Isolated-worktree development discipline: every task gets its own branch, auto-clean | — |
| [**ts-prebuild-check**](./skills/ts-prebuild-check) | Diff-only pre-commit validation for TypeScript: typecheck + lint changed files only | — |

### Image generation skills

Each skill is a self-contained visual style. Pick one, copy its prompt keywords, generate.

| Skill | What it generates |
|---|---|
| [**ancient-tea-room**](./skills/ancient-tea-room) | 古风茶室人像 |
| [**golden-hour-car-selfie**](./skills/golden-hour-car-selfie) | 黄金时刻车内自拍 |
| [**window-light-lifestyle**](./skills/window-light-lifestyle) | 窗边光生活方式 |
| [**social-cover**](./skills/social-cover) | 通用封面 — 生活方式 |
| [**wuxia-cinematic**](./skills/wuxia-cinematic) | 东方武侠电影感 |
| [**character-consistency**](./skills/character-consistency) | 人物一致性换装 — 锁定身份仅换场景 |
| [**logo-design**](./skills/logo-design) | Logo 设计 |
| [**product-detail**](./skills/product-detail) | 产品详情图 |
| [**product-scene**](./skills/product-scene) | 产品场景图 |
| [**promo-poster**](./skills/promo-poster) | 促销海报 |
| [**knowledge-card**](./skills/knowledge-card) | 科普图鉴/知识卡片 |
| [**cat-persona**](./skills/cat-persona) | 猫咪拟人角色 |
| [**chat-screenshot**](./skills/chat-screenshot) | 微信聊天截图 |

#### Female portrait routes（20 条人像路线）

| Route | Style |
|---|---|
| [**ancient-lady-dewy-makeup**](./skills/female-portrait-routes/beauty/ancient-lady-dewy-makeup.md) | 古风仕女水光妆 |
| [**low-key-cinematic-photography**](./skills/female-portrait-routes/cinematic/low-key-cinematic-photography.md) | 低调电影感摄影 |
| [**ecommerce-tryon**](./skills/female-portrait-routes/commercial/ecommerce-tryon.md) | 电商试穿 |
| [**black-pearl-dark-gold-ccd**](./skills/female-portrait-routes/curve/black-pearl-dark-gold-ccd.md) | 黑珍珠暗金 CCD |
| [**cold-white-clear-ccd-curve**](./skills/female-portrait-routes/curve/cold-white-clear-ccd-curve.md) | 冷白通透 CCD 曲线 |
| [**oriental-voluptuous**](./skills/female-portrait-routes/curve/oriental-voluptuous.md) | 东方丰腴 |
| [**pure-desire-curve**](./skills/female-portrait-routes/curve/pure-desire-curve.md) | 纯欲曲线 |
| [**soft-ccd-energetic-voluptuous**](./skills/female-portrait-routes/curve/soft-ccd-energetic-voluptuous.md) | 柔焦 CCD 活力丰腴 |
| [**bright-luxury-gufeng**](./skills/female-portrait-routes/fantasy/bright-luxury-gufeng.md) | 明艳华丽古风 |
| [**cold-xianxia-enhanced**](./skills/female-portrait-routes/fantasy/cold-xianxia-enhanced.md) | 冷感仙侠增强 |
| [**gufeng-xianxia**](./skills/female-portrait-routes/fantasy/gufeng-xianxia.md) | 古风仙侠 |
| [**sporty-active**](./skills/female-portrait-routes/fashion/sporty-active.md) | 运动活力 |
| [**studio-retouched**](./skills/female-portrait-routes/fashion/studio-retouched.md) | 影楼精修 |
| [**urban-fashion**](./skills/female-portrait-routes/fashion/urban-fashion.md) | 都市时尚 |
| [**clean-lifestyle**](./skills/female-portrait-routes/lifestyle/clean-lifestyle.md) | 干净生活方式 |
| [**french-lazy**](./skills/female-portrait-routes/lifestyle/french-lazy.md) | 法式慵懒 |
| [**retro-hongkong**](./skills/female-portrait-routes/lifestyle/retro-hongkong.md) | 复古香港 |
| [**travel-vacation**](./skills/female-portrait-routes/lifestyle/travel-vacation.md) | 旅行度假 |
| [**new-chinese**](./skills/female-portrait-routes/oriental/new-chinese.md) | 新中式 |
| [**ultra-close-real-face**](./skills/female-portrait-routes/realism/ultra-close-real-face.md) | 超近真实面部 |

### Video generation skills

| Skill | What it generates |
|---|---|

## Quick start

```bash
git clone https://github.com/webkubor/agent-skills.git
```

> 📋 **入库规范**：[`docs/SKILL-SPEC.md`](docs/SKILL-SPEC.md) — 目录结构/脱水规则/质量追踪/检查清单，所有 Agent 必读。

Then mount the skills into your runtime — see **[docs/INSTALL.md](./docs/INSTALL.md)** for Claude Code, Codex, Gemini CLI, Cursor and generic harnesses. The short version:

- **Claude Code**: copy a skill folder into `~/.claude/skills/` (or a project's `.claude/skills/`).
- **Codex / Gemini CLI / others**: reference the `SKILL.md` from your agent instructions file (`AGENTS.md`, `GEMINI.md`, system prompt) — the body is plain markdown procedure.

## Philosophy: skills are capabilities, not configs

A skill should survive the tool it was written on. What stays constant across agent products is the *procedure*: when to trigger, what evidence to collect, what "done" means, what must never be done (e.g. never read passwords from screenshots). That's what these files encode. If tomorrow's agent reads YAML instead of markdown, the procedure ports; the config wouldn't.

> Most skill bodies are currently written in Chinese (they are living production documents). English translations are being added progressively — the frontmatter `description` of every skill is already in English, which is what most agents use for routing.

## The wider toolkit

These skills are one layer of a larger local-first agent toolchain:

- [**vite-plugin-agent-eyes**](https://github.com/webkubor/vite-plugin-agent-eyes) — the runtime telemetry layer the agent-eyes skill reads
- [**browser-harness**](https://www.npmjs.com/package/browser-harness) — the CDP browser CLI behind browser-verify
- [**keyring**](https://github.com/webkubor/keyring) — store secrets once, agents never see plaintext (AES-256-GCM); the missing piece when a skill needs credentials
- [**voice-editor**](https://github.com/webkubor/voice-editor) — local Chinese TTS workstation with an agent-callable interface (Qwen3-TTS)
- [**typora-Bloom-theme**](https://github.com/webkubor/typora-Bloom-theme) — where the project-maturity-audit lessons were learned, live
- More writing at [webkubor.online](https://webkubor.online)

## License

[MIT](./LICENSE) — use them, fork them, ship them.

If a skill saves you a debugging session, a ⭐ helps others find it.
