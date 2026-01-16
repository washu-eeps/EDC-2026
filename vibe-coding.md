---
title: Vibe Coding Guidelines
---

# Vibe Coding Guidelines

We encourage using an LLM to generate code so you can focus on the scientific and computational ideas. This is allowed. What is not allowed is treating generated code as correct by default.

These rules apply to notebooks, scripts, cloud workflows, and command-line work. WashU provides [AI resources](https://ai.wustl.edu) that can help you. 

## The five rules of vibe coding

### 1) Think first. Prompt second.
Before you ask for code, write a short spec (3–8 lines):

- Goal: what you are trying to compute or produce
- Inputs: data sources, file formats, parameters
- Outputs: expected files/plots/tables and where they will live
- Assumptions: units, coordinate systems, time ranges, “clean data” assumptions
- Verification: what checks would convince you it worked

Why this matters: most “LLM coding failures” are actually unclear specs.

### 2) Go small.
Work in small, testable steps:

- Generate one chunk of code
- Run it
- Confirm it did what you expected
- Only then move to the next chunk

In cloud settings, always start with a small sample or a small spatial/temporal subset before scaling up.

### 3) Trust nothing without checking.
You must verify correctness. Minimum checks:

- A tiny “toy” case where you already know the answer (or can compute it by hand)
- An edge case (empty file, missing values, single-row input, extreme parameter)
- A sanity check on outputs (ranges, units, shapes, counts, plots)

If you cannot explain why the result is plausible, treat it as incorrect until proven otherwise.

### 4) You own the consequences.
You are responsible for:

- Cost: avoid accidentally running large jobs; monitor usage; stop what you don’t need
- Security: never paste secrets/keys into a prompt or notebook; use least-privilege credentials
- Data handling: don’t overwrite raw data; write outputs to clearly labeled locations
- Failure modes: avoid silent failures; make errors visible and interpretable

If something would be risky to run on a shared system, it is risky in the cloud too.

### 5) No explanation = no credit.
If you submit code, you must be able to explain:

- What each major step does (in plain language)
- Why it answers the spec
- What assumptions it makes
- The main limitations and likely failure modes

If you cannot explain your own pipeline, you have not finished the assignment.

## A practical workflow that satisfies the rules

1. Write the spec (short).
2. Ask for a plan/pseudocode that matches the spec.
3. Implement one step at a time.
4. After each step, add one verification check.
5. Only scale up after the small-case run is correct.

## What to include in submissions (recommended)

- A short “Verification” section: what you checked and what you observed
- A “Known limitations” note: what might break or be wrong
- A brief note on LLM assistance (what you asked it to do)

## Common failure modes to watch for

- Wrong units or coordinate reference system
- Silent type conversions (strings to numbers, NaNs dropped, integer overflow)
- Off-by-one indexing, time-zone or date parsing errors
- Data leakage (train/test contamination) in ML workflows
- Accidental large-scale compute (looping over full-resolution data unintentionally)

## If you are unsure

Stop and reduce scope:

- Run on 1–5 files instead of all files
- Run on a small region / short time window
- Print intermediate outputs
- Ask for an explanation of what the code is doing, then verify it yourself

Being cautious and correct beats being fast and wrong.
