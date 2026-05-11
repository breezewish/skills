# Personal useful skills

## Usage

```shell
npx skills add -g breezewish/skills
```

&nbsp;

---

&nbsp;

**[$codex-review](skills/codex-review/SKILL.md): Run code review using fresh Codex CLI**

It uses a fresh Codex session + Codex's built-in review prompt.

Why not simply call `codex exec review` directly? Because this skill calls Codex CLI with **denoised output**, which greatly saves tokens and avoid polluting your main context.

Example:

```
$codex-review Review commits in recent 2 days
$codex-review Review commits against main branch
```

&nbsp;

**[$simplify](skills/simplify/SKILL.md): Code simplification and cleanup**

(Nearly) the same prompt as Claude Code's `/simplify` command.

Example:

```
$simplify commits in recent 2 days
```
