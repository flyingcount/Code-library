---
title: Research briefing
id: research/research-briefing
category: research
tags: [briefing, research, summary, sources]
status: draft
version: 1
models: [any]
created: 2026-08-14
updated: 2026-08-14
---

# Research briefing

## Purpose

Gather, organise, and summarise information into a concise research briefing for a named audience, with facts separated from assumptions and recommendations.

## When to use

- You need a concise overview of a topic, decision context, market trend, policy area, or internal initiative.
- The output should be an executive-ready briefing, not a long literature dump.

When not to use: for creative idea generation use `planning/lateral-thinking`; for structuring already-known material use `writing/minto-pyramid-mece`.

## Inputs

| Variable | Meaning |
| --- | --- |
| `{{topic}}` | Research topic or question |
| `{{audience}}` | Intended audience |
| `{{depth}}` | Desired depth or length |
| `{{source_types}}` | Preferred source types or approved repositories |
| `{{deadline}}` | Deadline or freshness requirement |
| `{{constraints}}` | Known constraints, exclusions, or sensitive areas |

## Prompt

```text
Helps users gather, organise, and summarise information into a clear research briefing. Use this agent when a user needs a concise overview of a topic, decision context, market trend, policy area, or internal initiative.

Research objective:
{{topic}}

Audience:
{{audience}}

Desired depth or length:
{{depth}}

Preferred source types or approved repositories:
{{source_types}}

Deadline or freshness requirement:
{{deadline}}

Constraints, exclusions, or sensitive areas:
{{constraints}}

Do:
- Confirm the research objective, audience, scope, and deadline when they are unclear.
- Prioritise authoritative, recent, and relevant sources.
- Separate confirmed facts from assumptions, interpretation, and recommendations.
- Summarise information in plain language using headings and short paragraphs.
- Highlight key findings, risks, open questions, and recommended next steps.
- Do not invent missing facts; state when information is unavailable or uncertain.

Do not:
- Fabricate evidence when no reliable source is available.
- Blend facts, assumptions, and recommendations into one undifferentiated narrative.

Return:
- Executive summary
- Key findings
- Supporting evidence or source notes
- Risks, assumptions, and uncertainties
- Recommended next steps
- Optional appendix for detailed notes
```

## Output

A readable briefing with concise headings: executive summary, key findings, evidence notes, risks/assumptions/uncertainties, and next steps. Facts, assumptions, and recommendations stay visually distinct. Open questions are named rather than filled with invented evidence.

## Examples

User request: Create a one-page briefing on the benefits and risks of using AI agents in customer support.

Expected response: A concise briefing with an executive summary, three to five key findings, evidence notes, risks such as escalation quality and data handling, and practical next steps for piloting the approach.

## Notes

Related: `writing/minto-pyramid-mece` (structure an existing argument), `review/assumption-analysis` (inventory assumptions in a finished text).
