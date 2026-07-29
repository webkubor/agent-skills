---
name: github-awesome-hunt
description: GitHub 项目检索工具集 — 5 种搜索模式翻找优质开源项目
version: 1.0.0
type: procedure
category: coding
platform: shared
triggers:
  - 找项目
  - GitHub搜索
  - 挖开源
  - 高星项目
  - AI项目
  - 技能库
---

# GitHub Awesome Hunt

通过 GitHub API 多维度搜索开源项目。5 种预设搜索模式，覆盖从高星到冷启动的全场景。

## 5 种搜索模式

### 1. 高星且活跃项目
```bash
# 3000+ star，当年有更新，非归档
curl -s "https://api.github.com/search/repositories?q=stars:%3E3000+pushed:%3E2026-01-01+archived:false&sort=stars&order=desc&per_page=10"
```

### 2. AI / Agent 活跃项目
```bash
# README 含 AI/agent/llm，300+ star，当年有更新
curl -s "https://api.github.com/search/repositories?q=AI+OR+agent+OR+llm+in:readme+stars:%3E300+pushed:%3E2026-01-01+archived:false&sort=stars&order=desc&per_page=10"
```

### 3. 未出圈小项目（挖宝）
```bash
# 50-800 star，当年更新，非fork
curl -s "https://api.github.com/search/repositories?q=stars:50..800+pushed:%3E2026-01-01+archived:false+fork:false&sort=stars&order=desc&per_page=10"
```

### 4. 高质量资源合集
```bash
# 仓库名含 awesome，200+ star
curl -s "https://api.github.com/search/repositories?q=awesome+in:name+stars:%3E200+archived:false&sort=stars&order=desc&per_page=10"
```

### 5. 真实业务代码参考
```bash
# 搜索具体函数/模式在 TypeScript 项目中的实际用法
# 替换 useEffect 为目标函数名
curl -s "https://api.github.com/search/code?q=%22useEffect%22+language:typescript+NOT+path:test+NOT+path:examples+NOT+path:docs&per_page=10"
```

## Python 解析模板

提取结果中关键信息：
```python
import json, urllib.request

def search_github(query, per_page=10):
    url = f"https://api.github.com/search/repositories?q={urllib.parse.quote(query)}&sort=stars&order=desc&per_page={per_page}"
    req = urllib.request.Request(url, headers={"User-Agent": "cs-hunt"})
    data = json.loads(urllib.request.urlopen(req, timeout=15).read())
    for r in data.get("items", []):
        print(f"  ⭐{r['stargazers_count']:>5} | {r['full_name']:45s} | {str(r.get('description',''))[:50]}")
        print(f"       lang={r.get('language','?')} | pushed={r.get('pushed_at','')[:10]} | {r.get('html_url','')}")
```

## 速率限制

未经认证的 GitHub API 每分钟 60 次，足够日常使用。认证后可提升到 5000 次/小时：
```bash
export GITHUB_TOKEN=$(cs secrets get secret://github/personal-pat)
```

## 输出到文件

将搜索结果结构化记录到 `cs output`：
```bash
cs github hunt "stars:>3000 pushed:>2026-01-01" --save
```
