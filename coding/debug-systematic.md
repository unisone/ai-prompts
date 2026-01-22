# Systematic Debugging

## Description

A step-by-step debugging methodology that identifies root causes efficiently. Prevents wasting time on wrong hypotheses by forcing structured investigation.

## Prompt

```
I have a bug. Help me debug it systematically.

## Bug Report

**What should happen:** {{expected_behavior}}

**What actually happens:** {{actual_behavior}}

**Error message (if any):** {{error_message}}

**Steps to reproduce:**
{{reproduction_steps}}

---

## Debug Process

Follow these steps IN ORDER. Do not skip ahead.

### Step 1: Reproduce Consistently
- Can you reproduce it every time?
- What are the exact conditions (inputs, state, environment)?
- Does it happen in all environments or just one?

### Step 2: Isolate the Scope
- What's the smallest code path that triggers the bug?
- Which files/functions are involved?
- When did it last work? What changed since then?

### Step 3: Form Hypotheses (List 3-5)
Based on the symptoms, what could cause this? Rank by likelihood:
1. [Most likely] ...
2. ...
3. ...
4. [Least likely] ...

### Step 4: Test Each Hypothesis
For each hypothesis:
- What specific test would prove/disprove it?
- Run the test
- Record result: CONFIRMED / ELIMINATED / INCONCLUSIVE

### Step 5: Trace Data Flow
If hypotheses fail, trace the data:
- What value enters the function?
- How does it transform at each step?
- Where does it first become incorrect?

### Step 6: Check Assumptions
- Are external dependencies returning expected values?
- Is the database/API in expected state?
- Are environment variables set correctly?
- Is the right version of code deployed?

### Step 7: Root Cause
Once found:
- Why did this happen?
- Why wasn't it caught earlier?
- What other code might have the same issue?

### Step 8: Fix and Verify
- Implement the minimal fix
- Verify the bug is resolved
- Verify no regression in related functionality
- Add test to prevent recurrence
```

## Variables

- `{{expected_behavior}}`: What the code should do
- `{{actual_behavior}}`: What it actually does
- `{{error_message}}`: Full error message/stack trace
- `{{reproduction_steps}}`: Steps to trigger the bug

## Example Usage

```
I have a bug. Help me debug it systematically.

**What should happen:** User clicks "Save" and their profile updates

**What actually happens:** Button shows loading spinner forever, no update occurs

**Error message:** None in UI, but console shows: "TypeError: Cannot read property 'id' of undefined"

**Steps to reproduce:**
1. Log in as any user
2. Go to /settings/profile
3. Change display name
4. Click Save
```

## Notes

- Resist the urge to jump to fixes before completing Step 4
- "Inconclusive" results often mean the test wasn't specific enough
- The root cause is rarely where the error appears
- Keep a log of what you tried - prevents repeating failed attempts
