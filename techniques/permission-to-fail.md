# Permission to Fail

> Give AI explicit permission to say "I don't know" — dramatically reduces hallucinations.

## When to Use

- Research or fact-finding tasks
- When accuracy is more important than completeness
- Technical questions outside common knowledge
- Any high-stakes decision

## Why It Works

AI models are trained to be helpful, which creates pressure to always provide an answer — even when they shouldn't. By explicitly giving permission to express uncertainty, you remove that pressure and get more honest responses.

Anthropic's documentation recommends: "Give the AI explicit permission to express uncertainty rather than guessing. This reduces hallucinations and increases reliability."

## The Prompt

### Basic Permission

```
[Your question]

If you're not certain, say so. I prefer "I don't know" or 
"I'm not sure" over a confident wrong answer.
```

### With Confidence Levels

```
[Your question]

For each part of your response, indicate your confidence:
- HIGH: Very confident, well-established knowledge
- MEDIUM: Reasonably confident but could be wrong
- LOW: Uncertain, would recommend verification
- UNKNOWN: Don't have reliable information

I'd rather know what you don't know than get a guess presented as fact.
```

### Comprehensive Uncertainty Framework

```
[Your question]

Answer what you know with confidence. For everything else:

1. If you're uncertain, say "I'm not sure about..."
2. If it's outside your training data, say "I don't have information about..."
3. If you're inferring/guessing, say "My best guess is... but verify this"
4. If it depends on context you don't have, ask me

Being wrong confidently is worse than being uncertain honestly.
```

## Example

### Without Permission to Fail

**Q:** What were Tesla's exact Q3 2024 revenue numbers by region?

**A:** Tesla's Q3 2024 revenue broke down as follows: North America $14.2B, Europe $5.8B, Asia Pacific $6.1B... *(confident but potentially hallucinated specifics)*

### With Permission to Fail

**Q:** What were Tesla's exact Q3 2024 revenue numbers by region?

If you're not certain about specific figures, say so.

**A:** I can tell you Tesla's total Q3 2024 revenue was approximately $25.2B, but I'm not confident about the exact regional breakdown. Tesla reports by segment (Automotive, Energy, Services) rather than geography in their public filings. For precise regional figures, I'd recommend checking their investor relations page or their 10-Q filing. [MEDIUM confidence on total, LOW on regional split]

## Variations

### For Code

```
Write [code request].

If you're not sure about:
- The exact API/syntax — mark it with // VERIFY: [reason]
- Whether it handles edge cases — note what you didn't test for
- Performance implications — flag concerns

I'll test it either way. Knowing where to look is helpful.
```

### For Research

```
Research [topic].

Distinguish between:
- Facts you're confident about (cite if possible)
- Reasonable inferences (mark as such)
- Speculation (clearly label)
- Knowledge gaps (tell me what you don't know)

A shorter, accurate answer beats a longer, unreliable one.
```

### For Advice

```
[Your question about a decision]

Feel free to:
- Say "it depends" and explain what it depends on
- Give a range instead of a false-precision answer
- Tell me you'd need more information
- Recommend consulting a specialist

I'm not looking for false certainty.
```

## The Honesty Modifiers

Add these to any prompt:

| Modifier | When to Use |
|----------|-------------|
| "If you don't know, say so" | Basic uncertainty permission |
| "Confidence levels please" | When you need to calibrate trust |
| "Mark guesses as guesses" | Research tasks |
| "What would you need to know?" | When answer seems uncertain |
| "What could be wrong here?" | Decision-making |

## Pro Tips

1. **Model good behavior** — Show that uncertainty is valued, not punished
2. **Ask follow-up** — "What would make you more confident?"
3. **Reward honesty** — Don't push back when AI says "I don't know"
4. **Verify flagged items** — Actually check the things marked uncertain

## What Changes

| Without Permission | With Permission |
|-------------------|-----------------|
| Confident hallucinations | Flagged uncertainties |
| False precision ("exactly 23.4%") | Honest ranges ("roughly 20-25%") |
| Made-up citations | Admitted gaps |
| Overreaching answers | Appropriately scoped responses |

## When to Skip

- Creative writing (you want imagination)
- Brainstorming (uncertainty kills flow)
- When you explicitly want speculation
- Casual conversation

## Effectiveness

| Task Type | Impact |
|-----------|--------|
| Factual research | ⭐⭐⭐⭐⭐ |
| Technical answers | ⭐⭐⭐⭐⭐ |
| Data/numbers | ⭐⭐⭐⭐⭐ |
| Analysis | ⭐⭐⭐⭐ |
| Creative work | ⭐ |

---

*Based on Anthropic's best practices documentation and hallucination research*
