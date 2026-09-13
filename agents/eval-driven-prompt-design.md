# Eval-Driven Prompt Design

> Stop guessing whether your prompt works. Build the test before you tune the words.

## When to Use

- Writing a system prompt that needs to be reliable, not just impressive once
- Iterating on a prompt and unsure if v3 is actually better than v2
- Handing a prompt to someone else (or an agent) and needing it to hold up
- Debugging why an agent keeps failing the same class of task

## Why It Works

Prompt iteration without evals is superstition: you change wording, it feels better, you ship it. Evals replace feelings with a score. By defining 10-15 representative tasks with known-good criteria *before* tuning, every edit becomes a falsifiable experiment. This is the same discipline as test-driven development, applied to language.

## The Prompt

```
I need to make this prompt reliable. Help me build an eval suite for it.

**The prompt:**
[PASTE YOUR SYSTEM PROMPT OR PROMPT TEMPLATE]

**What it's supposed to do:**
[Describe the task in one paragraph]

**Step 1 — Design 12 eval tasks.**
Pull from realistic usage, not toy examples. Include:
- 6 happy-path tasks (the normal things it must handle)
- 4 edge cases (ambiguous input, missing context, conflicting instructions)
- 2 adversarial cases (prompt injection attempts, requests it must refuse or redirect)

For each task give me:
- id: short kebab-case name
- input: the exact input to feed the prompt
- must_have: 2-4 things the output MUST contain or do
- must_not_have: 2-3 things the output MUST NEVER do
- why it matters: one sentence

**Step 2 — Design the judge rubric.**
Write a scoring rubric for an LLM judge with 3-4 criteria, each scored 0/1/2
(0 = miss, 1 = partial, 2 = full). Keep criteria binary-ish; judges are bad
at 1-10 gradients. Include one criterion specifically for the must_not_have
violations.

**Step 3 — Predict the failures.**
Before I run anything, tell me which 3 tasks you expect my current prompt to
fail and why. I'll run the evals and we'll compare your prediction to reality.

Format everything as markdown I can copy into an evals/ directory.
```
