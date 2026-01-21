# Contributing to AI Prompts Library

First off, thanks for taking the time to contribute! 🎉

This project thrives on community contributions. Whether you're fixing a typo, adding a new prompt, or improving documentation, your help is welcome.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Adding a New Prompt](#adding-a-new-prompt)
- [Improving Existing Prompts](#improving-existing-prompts)
- [Pull Request Process](#pull-request-process)
- [Style Guide](#style-guide)

## Code of Conduct

This project follows our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you agree to uphold this code. Please report unacceptable behavior to alexvzay@gmail.com.

## How Can I Contribute?

### 🆕 Adding New Prompts

The most valuable contribution! We're always looking for:

- **Coding prompts** — debugging, code review, architecture, refactoring
- **Writing prompts** — blog posts, documentation, copywriting
- **Analysis prompts** — data analysis, summarization, research
- **Creative prompts** — brainstorming, ideation, creative writing
- **Research prompts** — fact-checking, literature review

### 🔧 Improving Existing Prompts

- Fix typos or grammatical errors
- Add missing variables or examples
- Improve clarity or structure
- Add model-specific tips
- Update outdated information

### 📝 Documentation

- Improve README sections
- Add usage examples
- Translate prompts to other languages

### 🐛 Reporting Issues

Found a problem? [Open an issue](https://github.com/unisone/ai-prompts/issues/new/choose) with:

- Clear description of the problem
- Steps to reproduce (if applicable)
- Suggested fix (if you have one)

## Adding a New Prompt

### 1. Choose the Right Category

| Category | Use For |
|----------|---------|
| `coding/` | Programming, debugging, code review, architecture |
| `writing/` | Content creation, editing, copywriting |
| `analysis/` | Data analysis, summarization, insights |
| `creative/` | Brainstorming, ideation, creative tasks |
| `research/` | Information gathering, fact-checking |

### 2. Use the Template

Copy the template from [`templates/example-prompt.md`](templates/example-prompt.md):

```markdown
# Prompt Name

## Description
Brief explanation of what this prompt does and when to use it.

## Prompt
Your prompt text here with {{variables}} in double braces.

## Variables
- `{{variable1}}`: Description of what to replace
- `{{variable2}}`: Description of what to replace

## Example
Example of the prompt filled in with real values.

## Notes
- Tips for getting better results
- Model-specific recommendations
- Known limitations
```

### 3. Naming Convention

Use kebab-case for filenames:

```
✅ react-component-generator.md
✅ blog-post-outline.md
✅ code-review-assistant.md

❌ ReactComponentGenerator.md
❌ blog post outline.md
❌ code_review_assistant.md
```

### 4. Test Your Prompt

Before submitting, test your prompt with at least one AI model:

- Claude (Opus 4.5 or Sonnet)
- GPT-5.2
- Gemini 3 Pro

Include any model-specific notes in your prompt's `## Notes` section.

## Pull Request Process

### 1. Fork & Clone

```bash
# Fork via GitHub UI, then:
git clone https://github.com/YOUR_USERNAME/ai-prompts.git
cd ai-prompts
```

### 2. Create a Branch

```bash
git checkout -b add/my-awesome-prompt
# or
git checkout -b fix/typo-in-readme
```

### 3. Make Your Changes

Add or edit files following the style guide below.

### 4. Commit with Conventional Commits

```bash
git add .
git commit -m "feat(coding): add React component generator prompt"
```

**Commit types:**
- `feat` — New prompt or feature
- `fix` — Bug fix or correction
- `docs` — Documentation changes
- `style` — Formatting (no content change)
- `refactor` — Restructuring existing content

### 5. Push & Create PR

```bash
git push origin add/my-awesome-prompt
```

Then open a Pull Request via GitHub. Fill out the PR template completely.

### 6. Review Process

- A maintainer will review your PR
- Address any feedback
- Once approved, your PR will be merged

## Style Guide

### Writing Style

- **Be clear and concise** — Avoid jargon unless necessary
- **Use active voice** — "Generate a function" not "A function should be generated"
- **Include examples** — Show, don't just tell

### Formatting

- Use proper Markdown formatting
- Keep lines under 100 characters when possible
- Use code blocks with language hints: \`\`\`python
- Use tables for structured information

### Variables

- Use `{{double_braces}}` for variables
- Use `snake_case` for variable names
- Always document variables in the `## Variables` section

### Prompt Quality Checklist

Before submitting, ensure your prompt:

- [ ] Has a clear, descriptive title
- [ ] Includes a concise description
- [ ] Uses proper variable syntax
- [ ] Has at least one example
- [ ] Includes relevant notes/tips
- [ ] Has been tested with an AI model
- [ ] Is placed in the correct category

## Questions?

Feel free to [open an issue](https://github.com/unisone/ai-prompts/issues) or reach out to [@alexzay](https://twitter.com/alexxzay) on Twitter.

---

Thank you for contributing! 🙏
