---
name: github-launch-kit
description: Turn a GitHub repository or local codebase into an evidence-backed launch package with positioning, proof points, demo-video scripts, shot lists, README copy, and platform-specific social posts. Use when the user wants to introduce, launch, promote, market, announce, demo, or make a video about an open-source project; asks for a repo-to-video workflow; or requests a launch kit for GitHub, Xiaohongshu, WeChat Channels, Bilibili, X, Hacker News, or Product Hunt.
metadata:
  type: procedure
  category: coding
  platform: shared
---

# GitHub Launch Kit

Convert a repository into ready-to-produce launch material. Ground every claim in repository evidence, favor real product footage, and keep publishing under user control.

## Inputs

Accept any of:

- the current repository;
- a local repository path;
- a public GitHub URL;
- a private repository the user has authorized the current environment to read.

When the source is ambiguous, prefer the current repository and state that assumption. Ask only when choosing the wrong repository would create misleading output.

## Operating modes

Select the highest mode supported by the request and available tools:

1. **Content kit** — analyze the repository and create copy, scripts, and shot plans.
2. **Demo kit** — also run the project, capture screenshots or screen recordings, and replace planned proof with real proof.
3. **Rendered kit** — also assemble voiceover, captions, music, and video when suitable media tools are available.

Never claim a higher mode completed when its artifacts were not produced. Degrade gracefully and name what remains to be recorded or rendered.

## Workflow

### 1. Establish scope and safety

- Resolve the repository, requested language, audience, platforms, and desired duration.
- Default to Chinese copy and a 45–60 second vertical video when the user mentions Xiaohongshu or WeChat Channels.
- Treat repository inspection, local builds, and local artifact creation as authorized by the launch-kit request.
- Require explicit approval before publishing, uploading, messaging people, changing repository visibility, or using paid media-generation services.
- Never expose credentials, private source, customer data, local paths, internal hostnames, or unannounced features in public-facing artifacts.

### 2. Build an evidence ledger

Inspect the smallest useful source set first:

- `README*`, `LICENSE*`, package manifests, repository description, and release notes;
- screenshots, demos, docs, examples, and public website links;
- entry points and representative implementation files needed to confirm major features;
- installation and run commands.

Create a claim ledger before writing promotional copy:

| Claim | Evidence | Confidence | Public-safe |
|---|---|---|---|
| What the project does | file, URL, or observed behavior | high/medium/low | yes/no |

Do not invent traction, benchmarks, compatibility, users, pricing, security properties, or comparisons. Mark reasonable inference as inference.

### 3. Frame the launch story

Produce three short candidate angles:

- pain-first: the recurring problem;
- outcome-first: the visible result;
- builder-first: why or how it was built.

Choose the strongest evidence-backed angle unless the user selects one. Express the final story as:

`Audience → problem → distinctive mechanism → demonstrated result → call to action`

Prefer one memorable promise over a feature inventory.

### 4. Capture real proof

When demo capture is in scope:

- use the repository's documented package manager and run commands;
- avoid destructive setup and never use production credentials;
- record the shortest successful path that proves the main promise;
- hide secrets, personal data, notifications, bookmarks, and unrelated tabs;
- capture a clean start state, one core action, and the visible result;
- note failures honestly and fall back to repository screenshots when necessary.

Do not substitute generic AI imagery for product behavior when the project can be run. Generated imagery may support transitions or covers, but label it as illustrative.

### 5. Create `launch-kit/`

Write only deliverables relevant to the selected platforms. Use this default structure:

```text
launch-kit/
├── brief.md
├── claims.md
├── video/
│   ├── script-60s.md
│   ├── shot-list.md
│   ├── voiceover.md
│   └── captions.srt
├── social/
│   ├── xiaohongshu.md
│   ├── wechat-channels.md
│   ├── bilibili.md
│   ├── x.md
│   ├── hacker-news.md
│   └── product-hunt.md
├── github/
│   ├── readme-hero.md
│   └── demo-gif-plan.md
└── manifest.md
```

Omit empty files. Add actual images, GIFs, audio, and video beside these files only when produced.

#### `brief.md`

Include project summary, target audience, primary promise, chosen angle, tone, CTA, requested platforms, and known constraints.

#### `claims.md`

Include the evidence ledger, unverified assumptions, and claims deliberately excluded from public copy.

#### Video package

- Open with the problem or outcome in the first three seconds.
- Show the product by five seconds when real footage exists.
- Use one idea per scene and connect narration to visible proof.
- Keep a 60-second voiceover around 120–160 Chinese characters or 120–150 English words, then adjust to actual speech timing.
- Write the shot list as: time range, visual, action, narration, on-screen text, source asset.
- Generate valid SRT only after timings are known; otherwise use timestamp placeholders in `script-60s.md` and omit `captions.srt`.
- Avoid unsupported superlatives and generic phrases such as “颠覆行业” or “一键改变一切”.

#### Platform copy

Adapt the same verified story instead of copying identical text everywhere:

- **Xiaohongshu:** human hook, concrete before/after, short paragraphs, restrained tags, no fake personal experience.
- **WeChat Channels:** concise title, narration-friendly description, explicit value, simple CTA.
- **Bilibili:** searchable title, fuller context, chapters or bullet points when useful.
- **X:** compact claim, proof, repository link placeholder, optional short thread.
- **Hacker News:** factual title and builder context; avoid marketing language.
- **Product Hunt:** tagline, concise description, first comment, and maker story.

Use `[REPO_URL]`, `[DEMO_URL]`, and `[VIDEO_PATH]` placeholders when values are unavailable. Never fabricate links.

#### GitHub package

- Write a two-line README hero: what it does and who it helps.
- Propose one primary CTA and one proof asset.
- Keep `demo-gif-plan.md` under 30 seconds and focused on a single successful path.

#### `manifest.md`

List every requested deliverable with status: `ready`, `needs capture`, `needs render`, `needs user input`, or `blocked`. Include artifact paths and blockers.

### 6. Verify the kit

Before handoff:

- trace every public claim back to `claims.md`;
- confirm project name, commands, URLs, and feature names;
- check that copy fits the target platform and language;
- open produced images and videos to verify they are not blank, cropped, silent, or visibly broken;
- confirm sensitive data is absent;
- distinguish generated, captured, and planned assets;
- summarize the single recommended post and the next concrete action.

## Publishing boundary

Stop after producing and verifying the kit unless the user explicitly asks to publish. Before publishing, show the exact platform, account, title, copy, media path, and visibility for confirmation. Platform automation may break or violate platform rules; prefer official APIs and clearly identify browser-automation risk.

## Handoff format

Lead with the chosen launch angle and the artifact directory. Then report:

1. what is ready;
2. what was verified with real product evidence;
3. what still needs capture, rendering, credentials, or approval;
4. the recommended first platform and post;
5. the command or prompt the user can run next.

Keep the handoff concise. Do not dump every generated file into chat when clickable local links are available.
