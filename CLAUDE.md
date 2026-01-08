# CLAUDE.md - AI Prompts Library

## Overview
Battle-tested prompt library for Claude, GPT, and Gemini. Each prompt includes description, when to use, the prompt itself, why it works, and examples.

## Structure
```
coding/       # Software development prompts
techniques/   # General prompting techniques
writing/      # Content and documentation
analysis/     # Data and research
research/     # Market and competitor research
creative/     # Brainstorming and ideation
templates/    # Reusable templates
```

## Prompt Format
Every prompt file follows this structure:
- **Description**: What it does
- **When to Use**: Specific scenarios
- **Prompt**: The actual prompt (in code block)
- **Why It Works**: Explanation of technique
- **Example**: Before/after or usage demo

## Contributing
- One prompt per file
- Use kebab-case filenames
- Include all sections from format above
- Test prompt before submitting
- Update README quick reference table

## Commands
```bash
npm install     # Install dev deps
npm run lint    # Check markdown
npm run format  # Format files
```

## Quality Bar
- Prompts must be tested, not theoretical
- Include "Why It Works" with actual reasoning
- Examples should show real improvement
- No generic "act as expert" role-play fluff
