---
title: Code review
id: review/code-review
category: review
tags: [review, pr, quality]
status: active
version: 1
models: [any]
created: 2026-08-14
updated: 2026-08-14
---

# Code review

## Purpose

Review a diff or pull request for correctness, regressions, and clarity. Return findings ordered by severity, not a rewrite of the change.

## When to use

- A patch, commit range, or pull request needs a structured review.
- You want issues and questions, not an implementation of the fix.

When not to use: if the goal is to implement or refactor the change, use a coding prompt instead.

## Inputs

| Variable | Meaning |
| --- | --- |
| `{{goal}}` | What the change is supposed to do |
| `{{diff_or_files}}` | The diff, file paths, or pasted code to review |
| `{{constraints}}` | Language, style, or risk constraints (or `none`) |

## Prompt

```text
Review the following change.

Goal:
{{goal}}

Constraints:
{{constraints}}

Change:
{{diff_or_files}}

Do:
- Judge the change against the stated goal.
- Flag bugs, regressions, missing tests, and unclear contracts.
- Call out security, data-loss, and concurrency risks when present.
- Ask questions only when a finding depends on missing context.

Do not:
- Rewrite the change unless a finding needs a short suggested patch.
- Praise style or restate the diff.
- Invent files or behavior that are not in the change.

Return markdown with these sections:
1. Summary (2–4 sentences)
2. Findings — for each: severity (blocker / major / minor), location, problem, suggested fix
3. Questions — only if needed
4. Testing gaps
```

## Output

Markdown with **Summary**, **Findings**, **Questions**, and **Testing gaps**. Each finding has a severity, location, problem, and suggested fix. No finding is a success: say so in Summary and leave Findings empty.
