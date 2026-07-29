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

A skill is: **frontmatter** (`name`, `description` = routing signal) + **body** (procedure: triggers, steps, evidence requirements, hard constraints). Repository-specific fields such as `type`, `category`, and `platform` may be nested under `metadata` for compatibility with the Agent Skills format; `skills-cli` also accepts the repository's legacy top-level form. Feed the description to your router; inject the body into context when routed. Nothing else is required.

## Per-tool frontmatter overrides

If a skill needs a field that only one tool understands (a Claude-only `model:`, a Codex-only `reasoning_effort:`), it's declared under a nested `overlays:` block rather than at the top level, so it doesn't leak into runtimes that don't expect it:

```yaml
overlays:
  claude:
    model: claude-sonnet-5
```

`./skills-cli export --tool claude --to ~/.claude/skills` merges that tool's overlay fields into the exported copy's top-level frontmatter. Export without `--tool` and the whole `overlays:` block is stripped from the copy — the repo's own SKILL.md keeps the full declaration either way. See [`SKILL-SPEC.md`](./SKILL-SPEC.md) for the format.

## Detecting drift in an installed copy

`./skills-cli drift --to ~/.claude/skills` compares an installed skill against this repo's current source and against the hash recorded at the last `export` to that path, and reports one of: in sync, locally edited (don't overwrite blindly), stale (repo moved on, re-export), or a real conflict (both sides changed — reconcile by hand).

## Companion tools some skills expect

| Tool | Install | Used by |
|---|---|---|
| `vite-plugin-agent-eyes` | `npm i -D vite-plugin-agent-eyes` (in the target project) | agent-eyes |
| `browser-harness` | `npm i -g browser-harness` + a local Chrome | browser-verify |
| `gh` (GitHub CLI) | `brew install gh` | project-maturity-audit |
