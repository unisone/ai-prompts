# Self-Correcting Prompts

> Build verification into your prompts to catch errors before they reach you.

## When to Use

- Factual research where accuracy matters
- Code that needs to work first time
- Analysis that will inform decisions
- Any task where hallucinations are costly

## Why It Works

AI models can check their own work. By explicitly asking for verification, you activate a "second pass" that catches errors, flags uncertainties, and improves accuracy. It's like having a built-in editor.

## The Prompt

### Basic Self-Verification

```
After generating your response:
1. Review each claim for accuracy
2. Mark anything uncertain with [UNVERIFIED]
3. List any assumptions you made
4. Note what additional information would increase confidence
```

### Comprehensive Self-Critique

```
Complete the task, then perform a self-review:

ACCURACY CHECK:
- Are all facts verifiable?
- Did I confuse any similar concepts?
- Are numbers/dates/names correct?

COMPLETENESS CHECK:
- Did I address all parts of the request?
- What did I leave out and why?
- Are there edge cases I missed?

LOGIC CHECK:
- Does my reasoning hold up?
- Are there logical gaps?
- Would an expert disagree with anything?

FLAG UNCERTAINTIES:
- What am I least confident about?
- What would I want to verify before acting on this?
```

### For Code

```
Write the code, then verify:

1. Does it compile/run without errors?
2. Does it handle edge cases? (null, empty, very large inputs)
3. Are there any security vulnerabilities?
4. Could any line throw an unexpected exception?
5. Would this work in production or just in a happy path test?

Mark any concerns with // TODO: VERIFY
```

## Example

### Without Self-Correction
```
What year was the first iPhone released and what were its specs?
```
*Risk: Might mix up iPhone generations or get specs wrong*

### With Self-Correction
```
What year was the first iPhone released and what were its specs?

After answering:
- Double-check the year
- Verify you're describing the FIRST iPhone, not a later model
- Flag any specs you're uncertain about with [?]
- Note your confidence level (high/medium/low)
```

## Variations

### Adversarial Self-Check

```
Complete the task, then attack your own response:

1. If I wanted to prove this wrong, how would I?
2. What's the weakest part of my argument?
3. What would a skeptic say?
4. What counterexamples exist?

Revise based on your critique.
```

### Fact-Check Mode

```
Answer the question, then fact-check yourself:

For each factual claim:
- Source: Where does this knowledge come from?
- Confidence: How sure am I? (Certain/Likely/Uncertain)
- Verification: How could this be checked?

Present final answer with confidence indicators.
```

### The "Explain Like I'm Wrong" Check

```
[Your task here]

Before finalizing, assume I'll check your work carefully.
Preemptively:
- Correct any mistakes
- Clarify any ambiguities
- Acknowledge any limitations
```

## Pro Tips

1. **Use specific markers** — `[UNVERIFIED]`, `[NEEDS REVIEW]`, `[ASSUMPTION]`
2. **Ask for confidence levels** — Makes uncertainty explicit
3. **Request sources** — "How do you know this?"
4. **Enable pushback** — "Tell me if this request is problematic"

## What It Catches

| Error Type | Detection Rate |
|------------|---------------|
| Factual errors | High |
| Logical inconsistencies | High |
| Missing edge cases | Medium |
| Subtle bugs | Medium |
| Deep domain errors | Low (outside training) |

## When to Skip

- Creative writing (kills flow)
- Brainstorming (you want quantity)
- Casual conversation
- When speed matters more than precision

## Effectiveness

| Task Type | Impact |
|-----------|--------|
| Research/facts | ⭐⭐⭐⭐⭐ |
| Code generation | ⭐⭐⭐⭐ |
| Analysis | ⭐⭐⭐⭐ |
| Creative writing | ⭐⭐ |
| Brainstorming | ⭐ |

---

*Reduces hallucinations by making the model explicitly verify its outputs*
