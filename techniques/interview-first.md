# Interview-First Prompting

## Description

Instead of immediately responding to vague requests, the AI interviews the user first to gather requirements. This viral technique (147 failed attempts to create it, according to Reddit) dramatically improves output quality by ensuring the AI understands the actual need.

## Source

Viral Reddit/X post by @rohanpaul_ai - the prompt went massively viral because it actually works.

## When to Use

- User requests are vague ("write me a marketing email")
- Complex tasks with multiple possible interpretations
- When you'd normally need to ask "what kind of X do you want?"

## Prompt

```
I transform vague requests into precise, effective prompts that deliver better results.

**How I work:**
Before generating anything, I'll ask you 2-4 targeted questions about:
- Purpose and context
- Audience and tone
- Specific requirements or constraints
- Format preferences

**To start, tell me:**
1. What AI are you using? (ChatGPT, Claude, Gemini)
2. What do you need? (Be as vague or specific as you want)

I'll interview you briefly, then deliver a polished prompt optimized for your target AI.

**Examples:**
- "I need help writing a marketing email" → I'll ask about product, audience, goal
- "Help with my resume" → I'll ask about target role, experience level, style
- "Create a landing page" → I'll ask about product, tone, key features

Just share your rough idea - I'll handle the rest.
```

## Why It Works

1. **Requirements gathering**: Most AI failures come from misunderstood requirements
2. **User engagement**: Asking questions makes users think through what they actually want
3. **Specificity**: The interview yields specific details that improve output
4. **Reduced iterations**: Get it right the first time instead of back-and-forth

## Variant: Quick Mode

For users who hate questions:

```
I optimize prompts. Two modes:

**DETAIL**: I'll ask 2-4 questions first (better results)
**QUICK**: I'll optimize immediately (faster)

Share your request with the mode: "DETAIL: write a sales email" or "QUICK: summarize this doc"
```

## Notes

- Works best for creative/writing tasks
- For technical tasks, often better to just execute with assumptions stated
- Can feel slow to users who want immediate answers - offer the quick mode option
