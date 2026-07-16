# Mounting the skills / 挂载方式

The skill bodies are runtime-neutral markdown. Only this file knows about specific agent products.

## Claude Code

```bash
# user-level (all projects)
cp -r skills/<name> ~/.claude/skills/<name>

# or project-level
cp -r skills/<name> <your-project>/.claude/skills/<name>
```

Claude Code auto-discovers `SKILL.md` frontmatter (`name` + `description`) and routes on it. Invoke explicitly with `/<name>` when the skill declares `user-invocable: true`.

## Codex

Reference the skill from your `AGENTS.md`:

```markdown
## Skills
When the task matches the description below, read and follow the linked procedure.
- browser-verify — visual UI verification via real Chrome: see skills/browser-verify/SKILL.md
```

## Gemini CLI

Same pattern in `GEMINI.md`, or paste the skill body into a custom system instruction.

## Cursor / other IDE agents

Add the skill path to your rules file (e.g. `.cursor/rules/`) with an instruction to read it when the trigger condition matches.

## Generic harness

A skill is: **frontmatter** (`name`, `description` = routing signal) + **body** (procedure: triggers, steps, evidence requirements, hard constraints). Feed the description to your router; inject the body into context when routed. Nothing else is required.

## Companion tools some skills expect

| Tool | Install | Used by |
|---|---|---|
| `vite-plugin-agent-eyes` | `npm i -D vite-plugin-agent-eyes` (in the target project) | agent-eyes |
| `browser-harness` | `npm i -g browser-harness` + a local Chrome | browser-verify |
| `gh` (GitHub CLI) | `brew install gh` | project-maturity-audit |
