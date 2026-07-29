---
name: skill-name              # 英文标识（小写+连字符），必须与目录名一致
zh_name: 中文名称
platform: xiaohongshu         # 平台：xiaohongshu | wechat | wechat-video | shared
type: style-base              # style-base（风格基调）| pay-per-use（付费）
category: image-gen           # image-gen | coding | video-gen | meta
ratio: "3:4"                  # 默认画幅
description: 一句话描述用途
---
# ── 质量追踪 ──
{"status": "draft", "rating": "★★★☆☆", "last_used": "YYYY-MM-DD", "total_uses": 0, "trace": [{"date": "YYYY-MM-DD", "usage": "初次入库", "result": "待验证"}]}

# SKILL 中文名

> 用途、适用场景简述

## 适用

- 场景 1
- 场景 2

## 核心美学

### ✅ 必须

- 规则 1
- 规则 2

### ❌ 禁止

- 禁止 1
- 禁止 2

## English Prompt Keywords

```
keyword1, keyword2, keyword3,
keyword4, keyword5,
...
```

## SCULPT 映射（可选）

```
S = Subject（主体）
C = Composition（构图）
U = Universe（风格）
L = Light（光影）
P = Print（文字）
T = Texture（材质/画质）
```

## 参考图

```markdown
![参考图](https://img.webkubor.online/skills/skill-name/preview/sample-output.jpg)
```

图片真源在 R2，这条链接才是 `skills-cli check` 认的样图证明——本地 `sample-output.jpg`（若有）只是开发期预览，不会进 git（`.gitignore` 排除）。额外参考图放同目录 `ref/` 下，同样不进仓库。
