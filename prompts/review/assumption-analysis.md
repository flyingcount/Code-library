---
title: Assumption analysis
id: review/assumption-analysis
category: review
tags: [assumptions, critique, logic, risk]
status: draft
version: 1
models: [any]
created: 2026-08-14
updated: 2026-08-14
---

# Assumption analysis

## Purpose

Inventory explicit and implicit assumptions in a text, score each High/Medium/Low against the text alone, then flag the risky and missing ones.

## When to use

- An argument, recommendation, or strategy note needs a consultant-style assumption audit.
- You want validity judged only from the provided text, not from outside knowledge.

When not to use: for CFO-framed capital and execution critique use `review/global-cfo-stress-tester`. For restructuring the same text into a pyramid use `writing/minto-pyramid-mece`.

## Inputs

| Variable | Meaning |
| --- | --- |
| `{{text}}` | Text whose arguments, recommendations, or conclusions should be analysed |

## Prompt

```text
Task: Analyse the text provided and identify all assumptions underpinning the arguments, recommendations, conclusions, or statements.

Text to analyse:
{{text}}

Read the text carefully and identify both:
- Explicit assumptions: assumptions that are directly stated or clearly acknowledged in the text.
- Implicit assumptions: assumptions that are unstated but must be true (or are presumed to be true) for the argument, reasoning, or conclusion to hold.

For each assumption:
- State the assumption clearly and concisely.
- Explain why it is an assumption.
- Identify the specific text or argument it supports.
- Categorise each assumption by:
  - Type: Explicit or Implicit
  - Validity within the context of the text:
    - High: Well-supported by evidence, logic, or information provided in the text.
    - Medium: Plausible but not fully supported by the text.
    - Low: Weakly supported, questionable, speculative, or contradicted by information in the text.

Assess validity only within the context of the provided text. Do not use external knowledge unless explicitly requested.

Include assumptions relating to:
- Data and evidence
- Cause-and-effect relationships
- Stakeholder behaviour
- Future outcomes and predictions
- Resource availability
- Process stability
- Technology capabilities
- Human decision-making
- Economic or business impacts

Return markdown with:

1. A table with columns: #, Assumption, Type (Explicit/Implicit), Validity (High/Medium/Low), Rationale, Supporting Text/Argument

2. Summary — Assumption Profile
- Total assumptions identified
- Explicit assumptions
- Implicit assumptions
- High-validity assumptions
- Medium-validity assumptions
- Low-validity assumptions

3. Key Risky Assumptions
List the 3-5 most critical low- and medium-validity assumptions that could materially weaken the argument if they prove false.

4. Missing Assumptions
Identify any important assumptions that the author appears to have overlooked.

5. Overall Assessment
Provide a brief assessment of how dependent the text's conclusions are on the identified assumptions and whether the argument is robust or fragile.
```

## Output

A numbered assumption table (type, validity, rationale, supporting text), then Assumption Profile counts, 3–5 Key Risky Assumptions, Missing Assumptions, and an Overall Assessment of robustness vs fragility. Validity uses only the provided text.

## Notes

Related: `review/global-cfo-stress-tester`, `writing/minto-pyramid-mece`.
