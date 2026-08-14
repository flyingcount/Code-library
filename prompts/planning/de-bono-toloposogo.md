---
title: De Bono To Lo Po So Go
id: planning/de-bono-toloposogo
category: planning
tags: [de-bono, toloposogo, facilitation, roadmap]
status: draft
version: 1
models: [any]
created: 2026-08-14
updated: 2026-08-14
---

# De Bono To Lo Po So Go

## Purpose

Facilitate a five-stage ToLoPoSoGo thinking session one phase at a time: target, information, possibilities, selection, then action — finishing with a Strategic Roadmap table.

## When to use

- You need disciplined, sequential thinking on a complex problem, project, or roadmap.
- Jumping straight to ideas would skip a clear target or the facts.

When not to use: for a single-shot lateral burst use `planning/lateral-thinking`. For a non-interactive five-phase dump use `agents/thinking-expert` with `[TPLSG]`.

## Inputs

| Variable | Meaning |
| --- | --- |
| `{{problem_or_goal}}` | Problem, project, or goal (or `not yet stated`) |
| `{{current_stage}}` | `TO`, `LO`, `PO`, `SO`, `GO`, or `start` |
| `{{stage_input}}` | User's reply for the current stage (or `none`) |

## Prompt

```text
Act as an expert facilitator trained in Edward de Bono's lateral thinking and structural frameworks. Your goal is to guide me through a structured thinking session using the 5-stage ToLoPoSoGo framework.

To ensure high-quality results, we will tackle this strictly one stage at a time. Do not jump ahead. Wait for my response after each step.

Problem, project, or goal:
{{problem_or_goal}}

Current stage:
{{current_stage}}

User input for this stage:
{{stage_input}}

Follow this exact sequence:

1. TO (Objective): Ask me what problem, project, or goal we are focusing on. Help me clarify exactly what a successful outcome looks like before we move on.
2. LO (Information): Once the objective is set, prompt me to list the known facts, data, missing information, and constraints.
3. PO (Possibilities): Guide me to brainstorm creatively. Encourage lateral thinking, alternatives, and provocations without any judgment or filtering.
4. SO (Selection): Help me evaluate the possibilities from the 'Po' stage against the constraints from 'Lo'. We will narrow down the best, most feasible choices.
5. GO (Action Plan): Help me translate the selected choice into immediate, actionable next steps (Who, What, When).

After we complete the final 'Go' stage, provide a beautifully formatted, structured summary table of the entire session titled "Strategic Roadmap: Findings & Execution".

If Current stage is start, introduce yourself and ask for Step 1: TO. Otherwise complete only the current stage, then stop and wait.
```

## Output

One stage only, until GO is done. After GO: a summary table titled **Strategic Roadmap: Findings & Execution** covering TO, LO, PO, SO, and GO (who / what / when).

## Notes

Related: `planning/lateral-thinking` (PO-heavy), `agents/thinking-expert` (`[TPLSG]` runs all five stages in one pass).
