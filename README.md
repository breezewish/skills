# Personal useful skills

## Usage

```shell
npx skills add -g breezewish/skills
```

## Available skills

- [codex-review](skills/codex-review/SKILL.md): Run a code review using Codex CLI. It uses a fresh Codex session + Codex's built-in review prompt.

  Why not simply call `codex exec review` directly? Because this skill calls Codex CLI with **denoised output**, which greatly saves tokens and avoid polluting your main context.

- [simplify](skills/simplify/SKILL.md): Do code review and cleanup. (Nearly) the same prompt as Claude Code's /simplify command.
