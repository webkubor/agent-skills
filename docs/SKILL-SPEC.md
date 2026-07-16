---
name: skill-spec
zh_name: SKILL 编写规范
description: agent-skills 仓库的 SKILL.md 编写标准、目录结构、参考图规范。所有 Agent 入库前必读。
type: meta
---

# SKILL 编写规范 v1.0

> 所有 Agent 入库 SKILL 前必须遵守本标准。入库=通过格式校验。

## 目录结构

```
skills/<skill-name>/
├── SKILL.md           # 唯一入口（必须）
├── sample-output.jpg  # 参考样图（必须，至少1张）
└── ref/               # 额外参考图（可选，不放仓库）
```

- 目录名 = `name` 字段，全小写英文，连字符分隔
- `sample-output.jpg` 固定文件名，作为目录内唯一展示图
- 图片格式：jpg（优先）或 png，单张 ≤ 2MB

## SKILL.md 格式

### Frontmatter（必须）

```yaml
---
name: skill-name              # 英文标识，全小写+连字符，与目录名一致
zh_name: 中文名称              # 不超过15字
description: 一句话描述         # 包含风格关键词，用于搜索匹配
type: style-base              # style-base | pay-per-use
platform: xiaohongshu         # xiaohongshu | wechat | wechat-video | shared
ratio: "3:4"                  # 默认画幅
category: 古装               # 古装 | 现代
---
```

### 正文结构（必须）

```markdown
# 中文名称

> 一句话定位：风格核心关键词

## 固定风格核心
（不可变部分：肌肤标准/光线风格/镜头参数/画面质感/配色基调/禁止元素）

## 可变参数
（表格：参数名 | 默认值 | 可替换为）

## 负面约束固定
（固定负面 prompt）

## 使用方式
固定风格核心 + 场景=X + 服装=Y + 动作=Z → 生成完整 prompt

## 参考图
![参考图](sample-output.jpg)
```

### 质量追踪（必须）

正文末尾 HTML 注释：

```html
<!-- tracking
{"status":"tested","rating":"★★★★★","last_used":"YYYY-MM-DD","total_uses":N,"trace":[...]}
-->
```

| 字段 | 值 | 说明 |
|------|-----|------|
| status | draft / tested / production | 投产才标 production |
| rating | ★☆☆☆☆ ~ ★★★★★ | 有样图 ≥ ★★★★ |
| last_used | YYYY-MM-DD | 最后使用日期 |
| total_uses | 整数 | 累计使用次数 |
| trace | 数组 | 每次使用的日期+用途+结果 |

## 分类体系

| 分类 | 适用场景 |
|------|---------|
| 🏯 古装 | 古风/仙侠/新中式/东方幻想 |
| 🏙️ 现代 | 生活照/街拍/自拍/CCD/电影感/商业海报/Logo |

## 脱水规则

用户提供的完整 prompt → 抽离为：

```
固定风格核心（不变）
  ├─ 人物类型标准
  ├─ 肌肤标准
  ├─ 光线风格
  ├─ 镜头/画质参数
  ├─ 配色基调
  └─ 禁止元素

可变参数（可替换）
  ├─ 场景
  ├─ 服装
  ├─ 动作
  ├─ 构图
  └─ 光线色调

负面约束固定（不变）
```

**禁止行为：**
- ❌ 把用户完整 prompt 原样存为 SKILL（场景/服装写死了无法复用）
- ❌ 编造用户没给的参数
- ❌ 编造参考图（只复制用户给的图）
- ❌ 漏掉参考图

## 入库检查清单

- [ ] 目录名 = `name` 字段
- [ ] 有 `sample-output.jpg`
- [ ] Frontmatter 字段完整
- [ ] 固定核心 ≠ 空
- [ ] 可变参数有表格
- [ ] 负面约束有内容
- [ ] 质量追踪 JSON 完整
- [ ] 分类正确（古装/现代）
- [ ] 无编造内容
