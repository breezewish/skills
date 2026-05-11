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

```
node scripts/review.js --cwd "<current working directory>" "<review prompt>"
```

The review script will start a new agent to do the review. It takes a lot of time to complete (e.g. > 30 minutes), so be patient, do not interrupt it unless you have a good reason to believe it's stuck (e.g. no progress for > 10 minutes). The review script is expected to progress updates.

3. Report the progress and review results, keep text unchanged.

## Available scripts

- **`scripts/review.sh`** — The main script that runs the review process
