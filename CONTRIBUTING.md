# Contributing to Agent Skills

感谢你的贡献！无论是修 bug、提 skill 还是改文档，都欢迎 👋

## 快速开始

```bash
git clone https://github.com/webkubor/agent-skills.git
cd agent-skills
./skills-cli check  # 确保当前所有 skill 通过校验
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

## PR 规范

- **一个 PR 只做一件事**：一个 skill / 一个 bugfix / 一个功能
- **commit message**：`feat: ...` / `fix: ...` / `docs: ...`
- **通过 CI**：PR 会自动跑 `skills-cli check`
- **更新文档**：新增 skill 必须同步更新 README 两张表

## Skill 质量要求

- `sample-output.jpg` 必须是该 skill 真实出图结果，不用概念图
- SKILL.md 必须包含完整的「固定风格核心」「可变参数」「负面约束」「使用方式」
- 质量追踪 comment 必须如实填写（status/rating/last_used）
