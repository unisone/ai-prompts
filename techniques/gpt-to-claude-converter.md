# GPT to Claude Prompt Converter

## Description

Claude performs better with XML-structured prompts while GPT prefers markdown. This meta-prompt converts GPT-style prompts to Claude-optimized format.

## Source

Based on Matt Shumer's viral prompt (@mattshumer_) and Anthropic's prompting guidelines.

## When to Use

- Migrating prompts from ChatGPT to Claude
- Prompts that work in GPT but underperform in Claude
- Building Claude-native applications

## Prompt

```
Convert this GPT-style prompt to be optimized for Claude.

**Claude Prompting Principles:**
1. Use XML tags to structure content: <context>, <instructions>, <examples>, <output_format>
2. Put the most important instructions at the end (recency bias)
3. Be direct - Claude responds well to clear, imperative instructions
4. Use role descriptions that are specific and actionable
5. Include examples in <example> tags when expecting specific formats
6. Separate data from instructions using XML tags

**Conversion Rules:**
- Wrap background info in <context></context>
- Wrap instructions in <instructions></instructions>
- Wrap examples in <examples></examples>
- Wrap expected output format in <output_format></output_format>
- Move critical instructions to the end
- Replace vague roles ("act as an expert") with specific behaviors
- Remove filler phrases ("I want you to", "Please")

**Original Prompt:**
[Paste GPT prompt here]

**Output:**
Provide the Claude-optimized version with explanations of key changes.
```

## Example Conversion

**GPT-style (before):**
```
I want you to act as an expert software architect. You have 20 years of experience designing scalable systems. Please help me design a notification system. Consider scalability, reliability, and cost. Think step by step and explain your reasoning.
```

**Claude-optimized (after):**
```xml
<context>
You are designing a notification system for a growing application.
Requirements: scalability, reliability, cost-effectiveness.
</context>

<instructions>
Analyze the notification system requirements and propose an architecture.
For each component:
1. Explain its purpose
2. Justify the technology choice
3. Describe how it handles failures
</instructions>

<output_format>
Structure your response as:
## Overview
[High-level architecture diagram in ASCII]

## Components
[For each component: purpose, tech choice, failure handling]

## Tradeoffs
[What you optimized for and what you sacrificed]
</output_format>

Design the notification system architecture.
```

## Key Differences

| GPT Style | Claude Style |
|-----------|--------------|
| Role-play heavy | Behavior-focused |
| Natural language structure | XML structure |
| Instructions anywhere | Critical instructions last |
| "Please", "I want" | Direct imperatives |
| Inline examples | `<example>` tagged |

## Notes

- Not all prompts need conversion - simple queries work fine as-is
- XML structure matters most for complex, multi-part prompts
- Test both versions - sometimes GPT-style works fine in Claude
- The converter is itself a prompt - you can ask Claude to do this
