<div align="center">

# 🧠 AI Prompts Library

**A curated collection of production-ready prompts for modern AI assistants**

[![Claude](https://img.shields.io/badge/Claude-Opus%204.5-blueviolet?style=flat-square&logo=anthropic)](https://anthropic.com)
[![GPT](https://img.shields.io/badge/GPT-4o-brightgreen?style=flat-square&logo=openai)](https://openai.com)
[![Gemini](https://img.shields.io/badge/Gemini-2.0-blue?style=flat-square&logo=google)](https://deepmind.google)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

[Quick Start](#-quick-start) • [Categories](#-categories) • [Contributing](#-adding-prompts) • [Best Practices](#-prompt-engineering-tips)

</div>

---

## ✨ What's Inside

Battle-tested prompts optimized for **Claude Code**, **Claude Opus 4.5**, **GPT-4o**, and other frontier models. Each prompt follows a consistent template with variables, examples, and usage notes.

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/unisone/ai-prompts.git

# Browse prompts by category
cd ai-prompts/coding
```

**Or** just copy any prompt directly from GitHub into your AI assistant of choice.

## 📁 Categories

| Folder | Description | Use Cases |
|--------|-------------|-----------|
| [`coding/`](./coding) | Programming & development | Code review, debugging, architecture, system prompts |
| [`writing/`](./writing) | Content creation | Blog posts, documentation, copywriting, editing |
| [`analysis/`](./analysis) | Data & research | Data analysis, summarization, insights extraction |
| [`creative/`](./creative) | Ideation & brainstorming | Creative writing, brainstorming, problem-solving |
| [`research/`](./research) | Information gathering | Fact-checking, literature review, competitive analysis |
| [`templates/`](./templates) | Reusable structures | Base templates for creating new prompts |

## 🎯 Featured Prompts

| Prompt | Category | Description |
|--------|----------|-------------|
| [Ultrathink Code Craftsman](./coding/ultrathink-code-craftsman.md) | Coding | Philosophy-driven prompt for elegant software craftsmanship |
| [Structured Reasoning Planner](./coding/structured-reasoning-planner.md) | Coding | Methodical reasoning with logical dependencies & risk assessment |

## 📝 Prompt Format

Every prompt follows this standardized structure:

```markdown
# Prompt Name

## Description
What this prompt does and when to use it.

## Prompt
The actual prompt text with {{variables}} for customization.

## Variables
- `{{variable}}`: What to replace it with

## Example
A filled-in example showing the prompt in action.

## Notes
- Tips for best results
- Model-specific recommendations
- Known limitations
```

## ➕ Adding Prompts

1. **Choose a category** — Pick the folder that best fits your prompt
2. **Create the file** — Use kebab-case naming: `my-awesome-prompt.md`
3. **Follow the template** — Copy from [`templates/example-prompt.md`](./templates/example-prompt.md)
4. **Test it** — Verify with at least one AI model before committing

### Naming Convention

```
<descriptive-name>.md

# Examples:
coding/react-component-generator.md
writing/blog-post-outline.md
analysis/sentiment-analyzer.md
```

## 💡 Prompt Engineering Tips

<details>
<summary><strong>🎭 Role & Persona</strong></summary>

Define a clear identity for the AI:
```
You are a senior software architect with 15 years of experience...
```
</details>

<details>
<summary><strong>📋 Structured Output</strong></summary>

Request specific formats for consistent results:
```
Respond in this JSON format:
{
  "summary": "...",
  "recommendations": ["..."],
  "confidence": 0.0-1.0
}
```
</details>

<details>
<summary><strong>🔗 Chain of Thought</strong></summary>

For complex reasoning, ask the model to think step-by-step:
```
Before answering, reason through:
1. What are the key constraints?
2. What are the possible approaches?
3. What are the trade-offs?
Then provide your recommendation.
```
</details>

<details>
<summary><strong>🎯 Few-Shot Examples</strong></summary>

Provide examples of desired input/output:
```
Example 1:
Input: "The product is okay"
Output: { "sentiment": "neutral", "score": 0.5 }

Example 2:
Input: "Absolutely love it!"
Output: { "sentiment": "positive", "score": 0.95 }

Now analyze: {{user_input}}
```
</details>

<details>
<summary><strong>⚡ 2026 Model-Specific Tips</strong></summary>

| Model | Optimization |
|-------|--------------|
| **Claude Opus 4.5** | Leverage extended thinking with `<thinking>` tags, use artifacts for code |
| **Claude Code** | Reference `CLAUDE.md` for project context, use TodoWrite for complex tasks |
| **GPT-4o** | Use system messages effectively, structured outputs with JSON mode |
| **Gemini 2.0** | Multimodal inputs work great, leverage grounding with Google Search |

</details>

## 🔧 Integration Ideas

### With Claude Code
```bash
# Reference prompts directly in CLAUDE.md
cat ai-prompts/coding/structured-reasoning-planner.md >> .claude/CLAUDE.md
```

### With Custom GPTs
Import prompts as system instructions when building custom GPT assistants.

### With API Calls
```typescript
const systemPrompt = await fetch(
  'https://raw.githubusercontent.com/unisone/ai-prompts/main/coding/ultrathink-code-craftsman.md'
).then(r => r.text());
```

## 📊 Stats

- **Total Prompts**: Growing collection
- **Categories**: 6
- **Last Updated**: January 2026

---

<div align="center">

**Built with 🧠 by [Alex Zaytsev](https://github.com/unisone)**

*Contributions welcome! Open a PR or issue.*

</div>
