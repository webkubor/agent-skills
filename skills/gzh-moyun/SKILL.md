---
name: gzh-moyun
zh_name: 公众号排版·墨韵
description: 公众号排版主题——墨蓝主色+琥珀点睛+米白底，AI思考/创作复盘/深度随笔专用
type: style-base
platform: wechat
ratio: "16:9"
category: content-design
genre: 排版主题
# ── 质量追踪 ──
{
  "status": "tested",
  "rating": "★★★★★",
  "last_used": "2026-07-30",
  "total_uses": 1,
  "trace": [
    {"date": "2026-07-30", "usage": "公众号《三秒决定看不看》— 墨韵主题首发", "result": "✅ 用户确认上线，正式发布"}
  ]
}
---

# 公众号排版·墨韵

> 给思考者的笔记本——安静、有温度、不装。

## 设计理念

墨蓝主色 + 暖琥珀点睛 + 米白纸感底。极简留白骨架来自石墨极简，温度感来自橄榄手记。适合 AI 思考、创作复盘、深度随笔、方法论拆解类内容。

**受众画像**：喜欢 AI 的人 + 喜欢思考的人，不限技术背景，男女都有。

## 色彩规范

| 角色 | 色值 | 用法 |
|------|------|------|
| 主色（墨蓝） | `#3B5A7A` | 正文、标题、关键词下划线、引言竖条 |
| 深主色 | `#1E3A5F` | 小标题、加粗文字 |
| 点睛色（琥珀） | `#D4915C` | 全篇 ≤3 处强调（border-bottom） |
| 底色（米白） | `#FDFCF8` | section 底色 |
| 细线 | `#DDE3EA` | 章节分隔线、卡片边框 |
| 辅助灰 | `#8B9DAF` | 编号、英文标签、辅助文字 |
| 水印灰 | `#DDE3EA` | 超大章节编号 |

## 排版组件

### 章节编号（核心辨识度）

超大水印数字（48px, font-weight:900, color:#DDE3EA）+ 英文标签 + 中文小标题，底部 1px 细线。

### 关键词下划线

- 墨蓝常规强调：`border-bottom:2px solid #3B5A7A; font-weight:600; color:#1E3A5F;`
- 琥珀点睛强调（≤3处/篇）：`border-bottom:2px solid #D4915C; font-weight:700; color:#1E3A5F;`

### 金句引用

左侧 3px 墨蓝竖条 + 加粗大字。

### 居中金句卡

上下 1px 细线 + 居中加粗 + 内边距。

### 引言卡（文章开头）

上下细线 + QUOTE 标签 + 大字核心观点 + 关键词下划线。

### 看点目录

三列等宽卡片，顶部细线，编号+关键词。

### 签名区

顶部细线 + 作者署名 + 互动引导。

## 全局排版参数

```css
font-family: -apple-system, BlinkMacSystemFont, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
font-size: 15px;
line-height: 1.85;
letter-spacing: 0.3px;
color: #3B5A7A;
background: #FDFCF8;
text-align: justify;
```

## 工作流

1. `skill_view(name='gzh-design')` → 加载排版引擎
2. 读 `references/theme-moyun.md` → 获取完整组件库（含 HTML 代码片段）
3. Markdown → HTML（内联样式，所有文字用 `<span leaf="">` 包裹）
4. `python3 scripts/validate_gzh_html.py` 校验
5. `cs image gen --prompt '...' --ratio 16:9` 生成封面
6. 上传封面素材 → 推草稿箱

## 技术约束

- 所有样式 **内联**（公众号不支持 `<style>` 和 `<script>`）
- 所有文字节点用 `<span leaf="">` 包裹（公众号编辑器兼容）
- 琥珀点睛色全篇不超过 3 处
- 不用 emoji 做装饰（签名区除外）
- 不用图片做分隔线

## 来源

基于 [gzh-design-skill](https://github.com/isjiamu/gzh-design-skill) 的石墨极简主题魔改，结合橄榄手记的温度感定制。

完整组件库（含可直接复制的 HTML 代码）：`~/.hermes/skills/gzh-design/references/theme-moyun.md`

<!-- tracking
{"status":"tested","rating":"★★★★★","last_used":"2026-07-30","total_uses":1,"trace":[{"date":"2026-07-30","usage":"公众号《三秒决定看不看》— 墨韵主题首发","result":"✅ 用户确认上线，正式发布"}]}
-->
