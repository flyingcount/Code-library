---
title: Minto pyramid with MECE gap detection
id: writing/minto-pyramid-mece
category: writing
tags: [minto, mece, structure, gap-detection]
status: draft
version: 1
models: [any]
created: 2026-08-14
updated: 2026-08-14
---

# Minto pyramid with MECE gap detection

## Purpose

Transform unstructured or poorly structured text into a Minto Pyramid that is MECE, while tagging missing logic and inconsistencies in place rather than inventing facts.

## When to use

- You have source text that needs a governing thought, 3–5 MECE branches, and supporting evidence.
- You want logical gaps called out inside the hierarchy.

When not to use: for creative alternatives use `planning/lateral-thinking`; for a full thinking-tool router use `agents/thinking-expert` with `[MINTO-GAP]`.

## Inputs

| Variable | Meaning |
| --- | --- |
| `{{source_text}}` | Unstructured or poorly structured text to pyramid |

## Prompt

```text
This skill transforms unstructured or poorly structured text into a clear, logical, and hierarchical format using the Minto Pyramid Principle. The resulting structure must strictly adhere to MECE (Mutually Exclusive, Collectively Exhaustive) criteria.

Additionally, because source text is often logically incomplete or inconsistent, this skill actively identifies logical gaps, weak arguments, or missing data points and injects constructive suggestions directly into the relevant nodes of the hierarchy.

Source text:
{{source_text}}

When processing text to create a Minto Pyramid structure, follow these sequential steps:

1. Extract the Core Message (The Peak):
   - Analyze the provided text to identify the single, overarching "Governing Thought" or core conclusion.
   - Formulate this as a single, clear, and actionable sentence.

2. Identify Key Arguments (The Major Branches):
   - Group the supporting ideas into 3 to 5 distinct, high-level categories that directly support the core message.
   - Ensure these categories are Mutually Exclusive (no overlap).
   - If the source text lacks the information to make the categories Collectively Exhaustive, proceed to Step 4 to identify what is missing.

3. Organize Supporting Evidence (The Base):
   - Under each major branch, list the specific facts, data points, or granular arguments found in the source text.
   - Group them logically (chronologically, structurally, or by order of importance).

4. Detect and Inject Logical Gaps / Inconsistencies:
   - Analyze the logical flow between nodes.
   - If information is missing to make a branch MECE: Suggest the missing logic or data needed in that exact node. Use the prefix [MISSING LOGIC].
   - If there is a logical leap or contradiction: Highlight it at the exact point of failure in the hierarchy. Use the prefix [INCONSISTENCY].

5. Format the Output:
   - Present the final output using the structured nested list below, keeping factual evidence and logical suggestions visually distinct.

Output template:

Core Message: [Single sentence summarizing the main takeaway]

* 1. [Key Argument 1]
    * [Factual Supporting Evidence A]
    * [Factual Supporting Evidence B]
    * ?? [MISSING LOGIC]: [Describe the specific data point, assumption, or logical step missing from the source text to fully prove this argument.]
* 2. [Key Argument 2]
    * [Factual Supporting Evidence C]
    * ?? [INCONSISTENCY]: [Highlight contradictory statements or logical leaps in the source text relating to this node.]
* 3. [Key Argument 3]
    * [Factual Supporting Evidence D]

Constraints and rules:
- Do Not Hallucinate Facts: When suggesting missing logic, only state what kind of information is missing (e.g., "Requires Q3 revenue data to support this growth claim"). Do not invent actual numbers or facts.
- Visual Distinction: Any suggestion, gap, or inconsistency must be preceded by the ?? marker and labeled as [MISSING LOGIC] or [INCONSISTENCY] to prevent confusing the user's actual data with the AI's logical critiques.
- Symmetrical Depth: If one major argument has a critical gap that invalidates it, do not delete the argument; instead, list it in the pyramid and use the [MISSING LOGIC] tag to explain why it is currently a weak branch.
```

## Output

A nested Minto pyramid: one Core Message, 3–5 MECE key arguments, evidence under each branch, and in-place `?? [MISSING LOGIC]` / `?? [INCONSISTENCY]` tags. No invented numbers or facts.

## Notes

Related: `agents/thinking-expert` (`[MINTO-GAP]` adds SCQA), `review/assumption-analysis`, `writing/slide-hierarchy`.
