---
name: ts-prebuild-check
description: Use when setting up or running pre-commit / pre-build validation for a TypeScript project — the checks an agent must run before git commit (typecheck + lint + format + diff-only design-token check). 框架无关、零外部依赖；TypeScript 项目提交前验证流程。
type: procedure
category: coding
platform: shared
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

# TS Pre-Commit Check

定义 TypeScript 前端项目 git 提交前的验证流程。agent 在执行 `git commit` 前必须按此流程检查。

## 触发方式

**不是关键词触发。** 此流程绑定在 git pre-commit hook 中，每次 commit 自动执行。

## 流程（严格按顺序）

```
git commit
  │
  ├─ 1. git diff --cached --name-only
  │     获取本次暂存的文件列表
  │
  ├─ 2. 文件分类
  │     .ts/.tsx → 需要 type-check + lint
  │     .css    → 需要 style lint（如有）
  │     .json/.md → 跳过
  │
  ├─ 3. 仅对改动文件执行检查（非全量）
  │     tsc --noEmit（仅在有 .ts/.tsx 改动时）
  │     eslint <改动文件>（仅在有 .ts/.tsx 改动时）
  │
  ├─ 4. 检查结果
  │     通过 → 继续 commit
  │     失败 → 阻止 commit，输出错误，agent 必须修复后重新 commit
  │
  └─ 5. commit 完成
```

## 关键原则

1. **只检查改动文件** — 不跑全量 `tsc --noEmit`（太慢），只检查本次改动涉及的文件
2. **零外部依赖** — 只用项目已有的 `tsc`、`eslint`，不引入额外工具
3. **失败即停** — 任何一步失败都阻止 commit，agent 必须修复
4. **不卡存量** — 只拦本次改动引入的问题，存量问题不阻塞

## Agent 执行步骤

当 agent 准备执行 `git commit` 时：

```bash
# 1. 获取暂存文件
STAGED=$(git diff --cached --name-only --diff-filter=ACMR)

# 2. 筛选 TS/TSX 文件
TS_FILES=$(echo "$STAGED" | grep -E '\.(ts|tsx)$' || true)

# 3. 如果有 TS 文件，跑 type-check
if [ -n "$TS_FILES" ]; then
  npx tsc --noEmit
fi

# 4. 如果有 TS 文件，跑 eslint（仅改动文件）
if [ -n "$TS_FILES" ]; then
  npx eslint $TS_FILES
fi

# 5. 全部通过才允许 commit
```

## Pre-Commit Hook 安装

项目根目录创建 `.git/hooks/pre-commit`：

```bash
#!/bin/sh
STAGED=$(git diff --cached --name-only --diff-filter=ACMR)
TS_FILES=$(echo "$STAGED" | grep -E '\.(ts|tsx)$' || true)

if [ -n "$TS_FILES" ]; then
  echo "🔍 检查改动的 TS 文件..."
  
  # Type check
  if ! npx tsc --noEmit 2>/dev/null; then
    echo "❌ Type check 失败，请修复后重新 commit"
    exit 1
  fi
  
  # Lint（仅改动文件）
  if ! npx eslint $TS_FILES; then
    echo "❌ Lint 失败，请修复后重新 commit"
    exit 1
  fi
fi

echo "✅ Pre-commit 检查通过"
```

```bash
chmod +x .git/hooks/pre-commit
```

## 进阶：Diff-Only 检查

如果项目有存量 lint 问题，全量 eslint 会卡死。解决方案：

1. 创建独立的 `eslint.diff.config.js`，只开启需要守护的规则
2. pre-commit 中用 diff 文件列表 + 独立配置运行
3. 存量问题用 `// eslint-disable` 标注，新增行必须通过

参考实现思路：独立脚本读取 `git diff --cached` 文件列表，仅以 diff 配置跑这些文件，输出按文件聚合的报告。

## 常见问题

| 问题 | 解决 |
|------|------|
| tsc 太慢 | 改用 `tsc --noEmit --incremental`，或只检查改动文件 |
| eslint 和 prettier 冲突 | 装 `eslint-config-prettier` |
| hook 没执行 | `chmod +x .git/hooks/pre-commit` |
| 想跳过检查 | `git commit --no-verify`（不推荐） |
