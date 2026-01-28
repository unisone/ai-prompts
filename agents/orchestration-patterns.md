# Agent Orchestration Patterns

> Coordinate multiple AI "agents" to tackle complex tasks that single prompts can't handle.

## When to Use

- Tasks requiring multiple expertise areas
- Complex projects with distinct phases
- When you need checks and balances
- Research + analysis + writing workflows

## Why It Works

Single-prompt AI struggles with complex, multi-faceted tasks. By mentally separating concerns into specialized "agents," you get deeper expertise in each area and natural quality checks between stages.

## The Prompt

### Basic Multi-Agent Pattern

```
This task requires multiple perspectives. Work through it as a team:

**Research Agent**: Gather all relevant information first. Be thorough.

**Analysis Agent**: Take the research and identify patterns, insights, and implications.

**Critic Agent**: Challenge the analysis. What's weak? What's missing? What could be wrong?

**Synthesis Agent**: Incorporate the criticism and produce the final output.

Show the work of each agent clearly labeled, then provide the final deliverable.
```

### Specialized Team Pattern

```
I need help with: [COMPLEX TASK]

Work through this as a specialized team:

**[EXPERT 1 ROLE]**: [What they focus on]
**[EXPERT 2 ROLE]**: [What they focus on]  
**[EXPERT 3 ROLE]**: [What they focus on]
**[COORDINATOR]**: Synthesize into final output

Each expert should:
1. State their perspective
2. Provide specific recommendations
3. Flag concerns in their domain

The coordinator should resolve conflicts and produce a unified recommendation.
```

## Example

### For Product Decisions

```
Should we build feature X?

Analyze this as a product team:

**Product Manager**: What problem does this solve? Who wants it? How does it fit our roadmap?

**Engineer**: How complex is this to build? What are the technical risks? What's the maintenance burden?

**Designer**: How does this affect UX? Does it add complexity? Can users discover it?

**Business Analyst**: What's the revenue impact? What's the opportunity cost of building this vs. something else?

**Devil's Advocate**: Why should we NOT build this? What are we missing?

Each role should give a clear recommendation (Build / Don't Build / Need More Info) with reasoning.

Then synthesize into a final recommendation with confidence level.
```

### For Content Creation

```
Create a blog post about [TOPIC].

Work through this as a content team:

**Researcher**: What are the key facts, stats, and examples? What do experts say?

**Strategist**: What angle will resonate? What's the hook? What action do we want readers to take?

**Writer**: Draft the post based on research and strategy.

**Editor**: Critique the draft. What's unclear? What's boring? What's missing?

**Final Writer**: Incorporate edits and polish.

Show each stage, then deliver the final post.
```

## Advanced Patterns

### The Debate Pattern

```
[DECISION OR QUESTION]

Stage a debate:

**Advocate**: Make the strongest case FOR this position
**Opponent**: Make the strongest case AGAINST this position
**Judge**: Evaluate both arguments fairly. Who made stronger points? What did each side miss?

Then provide a balanced recommendation based on the debate.
```

### The Red Team Pattern

```
[PLAN OR PROPOSAL]

Red team this proposal:

**Blue Team**: Present the plan and its expected benefits
**Red Team**: Attack the plan. Find every flaw, risk, and failure mode. Be adversarial.
**White Team**: Evaluate the Red Team's attacks. Which are valid? Which are overblown?

Revise the plan to address valid criticisms.
```

### The Expert Panel

```
[COMPLEX QUESTION]

Convene an expert panel:

**Academic Expert**: What does research say? What's the theoretical framework?
**Practitioner Expert**: What works in practice? What are the real-world constraints?
**Contrarian Expert**: What does everyone get wrong about this? What's the unconventional view?

Moderate a discussion, then summarize areas of agreement and disagreement.
```

## Pro Tips

1. **Name the agents clearly** — Helps the AI maintain distinct perspectives
2. **Give them specific mandates** — "Find flaws" produces better criticism than "review"
3. **Show handoffs explicitly** — "Now the Editor reviews the Writer's draft..."
4. **Request disagreement** — Agents that always agree aren't useful
5. **End with synthesis** — Don't leave it as a debate; decide

## When to Skip

- Simple, single-domain tasks
- When you need speed over thoroughness
- Quick questions with clear answers

## Effectiveness

| Task Type | Impact |
|-----------|--------|
| Complex decisions | ⭐⭐⭐⭐⭐ |
| Multi-disciplinary problems | ⭐⭐⭐⭐⭐ |
| Content creation | ⭐⭐⭐⭐ |
| Research & analysis | ⭐⭐⭐⭐ |
| Simple tasks | ⭐⭐ (overkill) |

---

*Based on multi-agent orchestration patterns from AI engineering research*
