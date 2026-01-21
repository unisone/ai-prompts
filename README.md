<div align="center">

```
   ╔═══════════════════════════════════════════════════════════════════════════╗
   ║                                                                           ║
   ║    █████╗ ██╗    ██████╗ ██████╗  ██████╗ ███╗   ███╗██████╗ ████████╗   ║
   ║   ██╔══██╗██║    ██╔══██╗██╔══██╗██╔═══██╗████╗ ████║██╔══██╗╚══██╔══╝   ║
   ║   ███████║██║    ██████╔╝██████╔╝██║   ██║██╔████╔██║██████╔╝   ██║      ║
   ║   ██╔══██║██║    ██╔═══╝ ██╔══██╗██║   ██║██║╚██╔╝██║██╔═══╝    ██║      ║
   ║   ██║  ██║██║    ██║     ██║  ██║╚██████╔╝██║ ╚═╝ ██║██║        ██║      ║
   ║   ╚═╝  ╚═╝╚═╝    ╚═╝     ╚═╝  ╚═╝ ╚═════╝ ╚═╝     ╚═╝╚═╝        ╚═╝      ║
   ║                                                                           ║
   ║            ██╗     ██╗██████╗ ██████╗  █████╗ ██████╗ ██╗   ██╗           ║
   ║            ██║     ██║██╔══██╗██╔══██╗██╔══██╗██╔══██╗╚██╗ ██╔╝           ║
   ║            ██║     ██║██████╔╝██████╔╝███████║██████╔╝ ╚████╔╝            ║
   ║            ██║     ██║██╔══██╗██╔══██╗██╔══██║██╔══██╗  ╚██╔╝             ║
   ║            ███████╗██║██████╔╝██║  ██║██║  ██║██║  ██║   ██║              ║
   ║            ╚══════╝╚═╝╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝              ║
   ║                                                                           ║
   ║                    ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄                        ║
   ║                    █  Production-Ready AI Prompts  █                      ║
   ║                    ▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀                        ║
   ║                                                                           ║
   ╚═══════════════════════════════════════════════════════════════════════════╝
```

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&weight=600&size=18&duration=3000&pause=1000&color=A855F7&center=true&vCenter=true&multiline=true&repeat=true&width=600&height=80&lines=%F0%9F%A7%A0+Curated+prompts+for+frontier+AI+models;%E2%9A%A1+Claude+Opus+4.5+%7C+GPT-4o+%7C+Gemini+2.0;%F0%9F%9A%80+Copy.+Paste.+Ship." alt="Typing Animation" />

<br/>

[![Claude](https://img.shields.io/badge/Claude-Opus%204.5-blueviolet?style=for-the-badge&logo=anthropic)](https://anthropic.com)
[![GPT](https://img.shields.io/badge/GPT-4o-brightgreen?style=for-the-badge&logo=openai)](https://openai.com)
[![Gemini](https://img.shields.io/badge/Gemini-2.0-blue?style=for-the-badge&logo=google)](https://deepmind.google)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

<br/>

[⚡ Quick Start](#-quick-start) • [📁 Categories](#-categories) • [➕ Contributing](#-adding-prompts) • [💡 Best Practices](#-prompt-engineering-tips)

<br/>

```
┌──────────────────────────────────────────────────────────────┐
│  > prompt --load ultrathink-code-craftsman.md               │
│  ✓ Loaded: Ultrathink Code Craftsman                        │
│  ✓ Model: claude-opus-4-5                                   │
│  ✓ Mode: Extended Thinking                                  │
│  > Ready to craft elegant solutions_                        │
└──────────────────────────────────────────────────────────────┘
```

</div>

---

## ✨ What's Inside

Battle-tested prompts optimized for **Claude Code**, **Claude Opus 4.5**, **GPT-4o**, and other frontier models. Each prompt follows a consistent template with variables, examples, and usage notes.

```
  ┌─────────────────────────────────────────────────────────────────┐
  │                                                                 │
  │   📦 PROMPT ANATOMY                                             │
  │   ─────────────────                                             │
  │                                                                 │
  │   ┌───────────────┐                                             │
  │   │  # Title      │ ← What it's called                          │
  │   ├───────────────┤                                             │
  │   │  Description  │ ← What it does                              │
  │   ├───────────────┤                                             │
  │   │  Prompt       │ ← The actual prompt text                    │
  │   ├───────────────┤                                             │
  │   │  {{vars}}     │ ← Customizable placeholders                 │
  │   ├───────────────┤                                             │
  │   │  Examples     │ ← Real usage samples                        │
  │   ├───────────────┤                                             │
  │   │  Notes        │ ← Tips & model recommendations              │
  │   └───────────────┘                                             │
  │                                                                 │
  └─────────────────────────────────────────────────────────────────┘
```

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/unisone/ai-prompts.git

# Browse prompts by category
cd ai-prompts && ls -la coding/
```

**Or** just copy any prompt directly from GitHub into your AI assistant of choice.

## 📁 Categories

```
ai-prompts/
│
├── 💻 coding/        # Code review, debugging, architecture, system prompts
│   ├── ultrathink-code-craftsman.md
│   └── structured-reasoning-planner.md
│
├── ✍️  writing/       # Blog posts, documentation, copywriting, editing
│
├── 📊 analysis/      # Data analysis, summarization, insights extraction
│
├── 🎨 creative/      # Creative writing, brainstorming, problem-solving
│
├── 🔬 research/      # Fact-checking, literature review, competitive analysis
│
└── 📋 templates/     # Base templates for creating new prompts
    └── example-prompt.md
```

| Folder | Description | Use Cases |
|--------|-------------|-----------|
| [`coding/`](./coding) | Programming & development | Code review, debugging, architecture, system prompts |
| [`writing/`](./writing) | Content creation | Blog posts, documentation, copywriting, editing |
| [`analysis/`](./analysis) | Data & research | Data analysis, summarization, insights extraction |
| [`creative/`](./creative) | Ideation & brainstorming | Creative writing, brainstorming, problem-solving |
| [`research/`](./research) | Information gathering | Fact-checking, literature review, competitive analysis |
| [`templates/`](./templates) | Reusable structures | Base templates for creating new prompts |

## 🎯 Featured Prompts

<table>
<tr>
<td width="50%">

### 🧙‍♂️ Ultrathink Code Craftsman
**Category:** `coding/`

Philosophy-driven prompt that transforms AI from code generator to software craftsman. Think different. Obsess over details. Craft, don't code.

[→ View Prompt](./coding/ultrathink-code-craftsman.md)

</td>
<td width="50%">

### 🧠 Structured Reasoning Planner
**Category:** `coding/`

Methodical reasoning with 9-step framework: logical dependencies, risk assessment, abductive reasoning, and persistent problem-solving.

[→ View Prompt](./coding/structured-reasoning-planner.md)

</td>
</tr>
</table>

## 📝 Prompt Template

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

```
┌────────────────────────────────────────────────────────────────┐
│  CONTRIBUTION WORKFLOW                                         │
│  ════════════════════                                          │
│                                                                │
│  ① Choose category    →  coding/ writing/ analysis/ etc.      │
│  ② Create file        →  my-awesome-prompt.md                  │
│  ③ Follow template    →  templates/example-prompt.md           │
│  ④ Test with AI       →  Verify with at least one model       │
│  ⑤ Submit PR          →  Share with the community             │
│                                                                │
└────────────────────────────────────────────────────────────────┘
```

### Naming Convention

```bash
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

```
╔════════════════════════════════════════╗
║  📈 REPOSITORY STATS                   ║
╠════════════════════════════════════════╣
║  Total Prompts    │  Growing           ║
║  Categories       │  6                 ║
║  Last Updated     │  January 2026      ║
║  Compatibility    │  Claude, GPT, Gem  ║
╚════════════════════════════════════════╝
```

---

<div align="center">

```
╭─────────────────────────────────────────────────────────╮
│                                                         │
│   Built with 🧠 by Alex Zaytsev                        │
│   github.com/unisone                                    │
│                                                         │
│   ⭐ Star this repo if you find it useful!             │
│   🤝 Contributions welcome — open a PR or issue        │
│                                                         │
╰─────────────────────────────────────────────────────────╯
```

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&size=14&duration=4000&pause=2000&color=6B7280&center=true&vCenter=true&width=400&lines=prompt+%3E+think+%3E+ship+%3E+repeat" alt="Footer Animation" />

</div>
