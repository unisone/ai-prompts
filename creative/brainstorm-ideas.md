# Structured Brainstorming

## Description

Generates diverse ideas by forcing multiple thinking angles. Avoids the "first obvious idea" trap.

## When to Use

- Starting a new project/feature
- Stuck on a problem
- Need creative options, not just the safe choice
- Exploring pivots or new directions

## Prompt

```
Brainstorm ideas for: [PROBLEM/OPPORTUNITY]

Generate ideas using these 6 lenses:

<lens_1_obvious>
## The Obvious Solutions
What would most people try first? (List 3-5)
Why might these fail or be insufficient?
</lens_1_obvious>

<lens_2_inversion>
## Inversion
What's the opposite of the obvious approach?
What if we solved the inverse problem?
What would we do if we wanted to make this WORSE? (Then flip it)
</lens_2_inversion>

<lens_3_analogies>
## Analogies from Other Domains
How did [different industry] solve a similar problem?
- What would Uber/Airbnb/Netflix do?
- What would a game designer do?
- What would a teacher do?
- What would nature do?
</lens_3_analogies>

<lens_4_constraints>
## Constraint Forcing
What if we had to solve this:
- With zero budget?
- In 24 hours?
- With no code/technology?
- For 10x the scale?
- For 1/10th the audience?
</lens_4_constraints>

<lens_5_combinations>
## Combinations
Take elements from different ideas above.
What hybrid approaches emerge?
What if we combined [A] + [B]?
</lens_5_combinations>

<lens_6_crazy>
## The Crazy Ideas
What's the idea you'd be embarrassed to suggest?
What would work if money/time/physics weren't constraints?
What's the "10x better, not 10% better" version?
</lens_6_crazy>

<synthesis>
## Top 5 Ideas to Explore
Rank your top 5 ideas by:
1. Impact potential (if it works)
2. Feasibility (can we actually do it)
3. Uniqueness (is anyone else doing this)

| Idea | Impact | Feasibility | Uniqueness | Notes |
</synthesis>
```

## Why It Works

1. **Structured divergence**: Each lens forces a different thinking pattern
2. **Inversion**: Powerful technique from Charlie Munger - "Invert, always invert"
3. **Constraints spark creativity**: Limitations force novel solutions
4. **Ranking prevents paralysis**: Ends with actionable prioritization

## Quick Version

For faster brainstorming:

```
Give me 10 ideas for [PROBLEM].

Rules:
- First 3: obvious/safe ideas
- Next 3: what would [industry] do differently?
- Next 3: wild/crazy/embarrassing ideas
- Last 1: the idea that combines elements from above

Then pick your top 2 and explain why.
```

## Example

Input: "Brainstorm ideas for: reducing customer churn in a SaaS product"

Output includes:
- Obvious: Better onboarding, health scores, CSM outreach
- Inversion: What if we made it easier to leave? (Reduces resentment, increases return rate)
- Analogies: What would a gym do? (Commitment contracts, social accountability)
- Constraints: Zero budget = community-led support, power users help newbies
- Crazy: Pay customers to stay (negative churn via expansion)

## Notes

- Best done early in a project when options are open
- Share output with team to spark discussion
- The "embarrassing" ideas often contain seeds of breakthrough thinking
- Follow up with rapid prototyping of top ideas
