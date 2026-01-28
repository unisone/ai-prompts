# Plan-Then-Execute Pattern

> Separate planning from execution to dramatically improve complex task success rates.

## When to Use

- Multi-step tasks that often fail halfway through
- Projects where mistakes are expensive to fix
- When you want to review the approach before work begins
- Reducing AI costs (planning is cheaper than re-doing)

## Why It Works

Research shows the "Plan-and-Execute" pattern reduces AI costs by up to 90% compared to letting AI dive straight into execution. Why? Because catching a bad approach during planning is far cheaper than fixing a bad implementation.

The pattern also prevents AI from "tunnel visioning" on its first idea.

## The Prompt

### Basic Plan-Then-Execute

```
I need to: [TASK]

**PHASE 1 - PLANNING (do not execute yet)**

Create a detailed plan:
1. What are the steps to accomplish this?
2. What could go wrong at each step?
3. What information or resources do you need?
4. What's the definition of "done"?

Present the plan and wait for my approval before proceeding.

**PHASE 2 - EXECUTION (after I approve)**

Execute the approved plan step by step, checking off each item as you complete it.
```

### Detailed Planning Template

```
Before doing anything, create a comprehensive plan.

TASK: [What needs to be accomplished]

PLANNING PHASE:

1. **Goal Clarification**
   - What exactly are we trying to achieve?
   - What does success look like?
   - What's out of scope?

2. **Approach Options**
   - Option A: [approach]
   - Option B: [approach]
   - Recommended: [which and why]

3. **Step-by-Step Plan**
   - Step 1: [action] → Expected result: [result]
   - Step 2: [action] → Expected result: [result]
   - (continue...)

4. **Risk Assessment**
   - What could go wrong?
   - How will we detect problems?
   - What's the rollback plan?

5. **Dependencies & Prerequisites**
   - What do we need before starting?
   - What assumptions are we making?

6. **Definition of Done**
   - How will we know this is complete?
   - What are the acceptance criteria?

Present this plan. Do NOT proceed to execution until I confirm.
```

## Example

### For Code Changes

```
I need to refactor the authentication module to use JWT instead of sessions.

PHASE 1 - PLANNING (no code changes yet)

Create a migration plan:
1. What files need to change?
2. What's the order of changes to avoid breaking things?
3. What tests need to be updated?
4. How do we handle existing sessions during transition?
5. What's the rollback procedure?

Present the plan. I'll review before you touch any code.

PHASE 2 - EXECUTION (after approval)

Implement the approved plan, showing each step.
```

### For Research Projects

```
Research the competitive landscape for [PRODUCT CATEGORY].

PHASE 1 - RESEARCH PLAN

Before gathering any data, outline:
1. What specific questions are we answering?
2. What sources will you use?
3. How will you structure the findings?
4. What's the format of the final deliverable?
5. What are the known limitations of this research?

Present the research plan for my approval.

PHASE 2 - EXECUTION

Execute the approved plan, gathering and analyzing data.
```

### For Content Creation

```
Write a comprehensive guide about [TOPIC].

PHASE 1 - CONTENT PLAN

Create an outline:
1. What's the target audience?
2. What's the main takeaway?
3. What sections will you include?
4. What examples/evidence for each section?
5. What's the expected length?
6. What's the call to action?

Wait for outline approval before writing.

PHASE 2 - EXECUTION

Write the full guide following the approved outline.
```

## Advanced Patterns

### Plan-Review-Revise-Execute

```
[TASK]

Step 1: Create initial plan
Step 2: Critique your own plan - what's weak?
Step 3: Revise the plan based on critique
Step 4: Present revised plan for my approval
Step 5: Execute only after approval
```

### Checkpoint Pattern

```
[COMPLEX TASK]

Create a plan with checkpoints:

CHECKPOINT 1: [First milestone] - Stop and verify
CHECKPOINT 2: [Second milestone] - Stop and verify
CHECKPOINT 3: [Final milestone] - Stop and verify

At each checkpoint, summarize what was done and confirm before proceeding.
```

### Reversible Plan Pattern

```
[TASK]

Create a plan where every step is reversible:

For each step:
- Action: [what to do]
- Verification: [how to confirm it worked]
- Rollback: [how to undo if needed]

This ensures we can recover from any mistake.
```

## Pro Tips

1. **Actually review the plan** — The pattern only works if you provide feedback
2. **Ask "what could go wrong"** — Forces consideration of edge cases
3. **Request alternatives** — "What's another approach?" prevents tunnel vision
4. **Define "done" clearly** — Prevents scope creep and ambiguity
5. **Use checkpoints for long tasks** — Break execution into reviewable chunks

## Cost Savings

| Approach | Typical Outcome |
|----------|-----------------|
| Direct execution | 40% need significant rework |
| Plan-then-execute | 10% need rework |
| **Savings** | **~75% reduction in wasted effort** |

## When to Skip

- Quick, simple tasks
- Exploratory/creative work where planning kills spontaneity
- When you trust the AI's judgment completely
- Time-critical situations

## Effectiveness

| Task Type | Impact |
|-----------|--------|
| Code refactoring | ⭐⭐⭐⭐⭐ |
| Complex implementations | ⭐⭐⭐⭐⭐ |
| Research projects | ⭐⭐⭐⭐ |
| Content creation | ⭐⭐⭐⭐ |
| Quick tasks | ⭐⭐ |

---

*Based on AI agent research showing 90% cost reduction with planning patterns*
