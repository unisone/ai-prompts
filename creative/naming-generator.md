# Product/Feature Naming

## Description

Generates memorable names that pass the practical tests: available domains, easy to spell, appropriate connotations.

## When to Use

- Naming a new product or company
- Feature naming
- Project codenames
- Anything that needs a sticky name

## Prompt

```
Generate names for: [PRODUCT/FEATURE DESCRIPTION]

<context>
Target audience: [WHO]
Tone: [professional/playful/technical/friendly]
Category: [product/feature/company/project]
Constraints: [e.g., must be <8 characters, no numbers]
</context>

<generation_rounds>
## Round 1: Descriptive Names
Names that clearly describe what it does.
(Easy to understand, but may be generic)

## Round 2: Abstract Names  
Made-up words or unexpected combinations.
(Memorable, but meaning must be taught)

## Round 3: Metaphor Names
Names based on analogies or imagery.
(Evocative, but must fit the concept)

## Round 4: Mashups
Combine two relevant words creatively.
(Often catchy, but can feel forced)

## Round 5: Single Words
Real dictionary words repurposed.
(Simple, but domain availability challenging)
</generation_rounds>

<evaluation>
For each name, assess:
- [ ] Easy to spell after hearing it once
- [ ] Easy to pronounce in English
- [ ] No negative connotations in major languages
- [ ] .com or .io likely available (check 3-4 letter combos)
- [ ] Not too similar to major competitors
- [ ] Works as a verb? ("Let's [name] it")

## Top 5 Recommendations
| Name | Type | Pros | Cons | Domain guess |
</evaluation>
```

## Why It Works

1. **Multiple rounds**: Different naming strategies yield different options
2. **Evaluation criteria**: Prevents falling in love with impractical names
3. **Practical tests**: Domain availability, pronunciation matter in real world
4. **Structured output**: Easy to compare and discuss with team

## Quick Version

```
Generate 10 names for [THING]. 
Mix of: descriptive, abstract, and metaphor-based.
For each: rate domain availability likelihood (high/medium/low).
Star your top 3.
```

## Example

Input: "Generate names for: an AI tool that reviews code and suggests improvements"

Output includes:
- Descriptive: CodeReview AI, ReviewBot, PullChecker
- Abstract: Lintara, Codexa, Revvie
- Metaphor: CodeGuardian, PullPolish, MergeMintor
- Mashups: Codewise, Reviewly, Pullcraft
- Single words: Scrutiny, Refine, Polish

Top rec: "Codexa" - abstract, memorable, .com might be available, works as verb ("Codexa'd the PR")

## Notes

- Always verify domain availability (this prompt guesses)
- Check USPTO trademark database for finalists
- Test pronunciation with real humans
- Sleep on it - names grow or shrink on you
