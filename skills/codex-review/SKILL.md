---
name: codex-review
description: Run a code review using Codex CLI. Use when user asks for a code review.
---

# Review via Codex CLI

## Workflow

1. Assemble a review prompt.

Select one of the following review prompts based on the user request. If the user didn't specify, choose the most appropriate one based on the available information.

```
Review current code changes (staged, unstaged, and untracked files)
Review code changes against the base branch <...>
Review code changes introduced by commit <sha> (<title>)
Review code changes for commit range <sha1>..<sha2>
```

If you believe none of the above prompts are suitable, stop and ask the user for clarification.

2. Run the review script:

```shell
node scripts/review.js --cwd "<project directory>" "<review prompt>"
```

The review script will start a new agent to do the review. It takes a lot of time to complete (e.g. > 1 hour), so be patient, do not interrupt it.

Note: `scripts/review.js` lives inside this skill's directory, instead of project directory.

3. Just report what script outputs, keep text unchanged. The script may output progress texts as the review goes.

## Principles

- Never do review by yourself. Always run the review script and just report the progress and results. If review script fails or stucks, report to user and ask for next steps.
- Never regard script as stuck until it has no progress for > 30 minutes.
- Never regard script as failed even if it outputs errors or fails. It will try to recover by itself. Script kills itself if it really fails.
