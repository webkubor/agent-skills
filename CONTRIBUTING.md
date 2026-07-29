# Contributing to Agent Skills

感谢你的贡献！无论是修 bug、提 skill 还是改文档，都欢迎 👋

## 快速开始

```bash
git clone https://github.com/webkubor/agent-skills.git
cd agent-skills
./skills-cli check  # 确保当前所有 skill 通过校验

# 可选：本地提交前自动跑 diff-only 校验（只查本次改动的技能，不会被仓库历史欠账挡住）
git config core.hooksPath .githooks
```

## 贡献方式

### 新增 Skill

1. 创建 `skills/<skill-name>/` 目录
2. 按 [`SKILL-SPEC.md`](./docs/SKILL-SPEC.md) 编写 `SKILL.md`
3. 添加至少一张 `sample-output.jpg`
4. 更新 `README.md` 和 `README.zh-CN.md` 的技能表
5. 运行 `./skills-cli check` 确认零硬伤
6. 提交 PR

### 修复 Bug

1. 先提 Issue 描述问题
2. 修复后确保 `./skills-cli check` 仍然通过
3. PR 标题加 `[fix]` 前缀

### 改进 CLI

`skills-cli` 是单文件 Python 脚本，修改后请确保向后兼容。

### 从别处（CortexOS / 其它私有技能库）移植 Skill

同一个技能名如果在两个地方各存一份、没人记录谁是谁的 fork，早晚会各自演化到认不出彼此——这是真实踩过的坑，不是假设。移植时当场做两件事：

1. **加一行 `origin:` frontmatter**，写清楚来自哪、哪天挪过来的（例：`origin: 移植自 CortexOS skills/xxx，2026-07-29`）
2. **当场决定这份要不要跟源头保持同步**，并把决定写下来（同一行 origin 里说清楚即可）：
   - 内容完全一致、以后也不打算独立演化 → 让 agent-skills 做 canonical source，源头那边改成 symlink 指过来，不留两份实体文件
   - 会针对这里的场景重写/裁剪 → 说明"已改写，不再同步"；如果改写后的东西已经不是原来那个技能了，**换个名字**，不要同名不同源——这条是从 CortexOS 自己的 SKILLS-REGISTRY.md 抄来的规矩，同样适用这里

## PR 规范

- **一个 PR 只做一件事**：一个 skill / 一个 bugfix / 一个功能
- **commit message**：`feat: ...` / `fix: ...` / `docs: ...`
- **通过 CI**：PR 会自动跑 `skills-cli check`
- **更新文档**：新增 skill 必须同步更新 README 两张表

## Skill 质量要求

- `sample-output.jpg` 必须是该 skill 真实出图结果，不用概念图
- SKILL.md 必须包含完整的「固定风格核心」「可变参数」「负面约束」「使用方式」
- 质量追踪 JSON 必须如实填写（status/rating/last_used/total_uses/trace）——`skills-cli check` 会校验它存不存在、格式对不对、字段值是不是占位符
- `category: coding` 的技能建议带 `version:` 字段，方便追踪这个技能本身的迭代（`skills-cli check` 会提醒，非强制）
- 想看全库的使用记录新鲜度（哪些技能好久没用/没记录），跑 `./skills-cli stats`
