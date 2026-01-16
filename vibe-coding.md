---
title: Vibe Coding Guidelines
---

# Vibe Coding Guidelines

LLMs may be used to generate code, but correctness must be established by you.

These rules apply to notebooks, scripts, cloud workflows, and command-line work. WashU provides [AI resources](https://ai.wustl.edu) that can help you. [Vibe coding](https://www.techtarget.com/searchcio/feature/Vibe-coding-What-IT-leaders-need-to-know) is new, and [best](https://www.leanware.co/insights/best-practices-ai-software-development) and [emerging](https://www.cloudflare.com/learning/ai/ai-vibe-coding/) practices are still emerging. EEPS has condensed these into five rules. 

## The five rules of vibe coding

### 1) Think first. Prompt second.
Before generating code, define the problem:

- What are the inputs?
- What is the expected output?
- What assumptions are you making?
- How will you know the result is correct?

Unclear prompts lead to confident but wrong code.

### 2) Go small.
Work in small, testable steps:

- Generate a minimal piece of code
- Run it
- Verify the result
- Then proceed

Always start with a reduced scope, small dataset, or simplified case before scaling up.

### 3) Trust nothing without checking.
You must verify correctness. At minimum:

- Test a simple case with a known or easily reasoned answer
- Test an edge case (empty input, extreme values, missing data)
- Sanity-check outputs (ranges, types, sizes, trends, plausibility)

Running successfully is not evidence of correctness.


### 4) You own the consequences.
You are responsible for the **behavior and correctness of the code itself**, regardless of who or what generated it.

This includes wrong answers, hidden assumptions, and silent failures.  
Code that runs but produces incorrect results is still your responsibility.

You are also responsible for secondary consequences (cost, data loss, security), but correctness comes first.


### 5) No explanation = no credit.
If you submit code, you must be able to explain:

- What each major step does
- Why it answers the original question
- What assumptions it relies on
- Where it might fail or give misleading results

If you cannot explain it, you do not understand it.

## A practical workflow that satisfies the rules

1. Write the spec (short).
2. Ask for a plan/pseudocode that matches the spec.
3. Implement one step at a time.
4. After each step, add one verification check.
5. Only scale up after the small-case run is correct.

## What to include in submissions

- A short **Verification** section: what you checked and what you observed
- A **Known limitations** note: what might break, fail silently, or give misleading results

## Common failure modes to watch for

- **Wrong assumptions**  
  Inconsistent units, conventions, or defaults.

- **Data changing silently**  
  Values dropped, rounded, or altered without notice.

- **Misalignment errors**  
  Things not lining up; off-by-one mistakes.

- **Edge cases**  
  Empty inputs, extreme values, or special cases breaking the logic.

- **False success**  
  Code runs but produces incomplete or misleading results.

## If you are unsure

Stop and reduce scope:

- Run on a very small subset instead of everything
- Simplify the problem or inputs as much as possible
- Print or inspect intermediate results
- Explain what each step is supposed to be doing, then verify that it actually does that

Being cautious and correct beats being fast and wrong.
