# AI Prompts Repo Enhancement Plan

**Research Date:** January 27, 2026  
**Current State:** 29 prompts across 5 categories  
**Goal:** Become the go-to prompt library for 2026

---

## 📊 Gap Analysis

### What You Have (Strong)
- ✅ Coding prompts (10) - solid coverage
- ✅ Techniques (8) - good fundamentals
- ✅ Clean structure with consistent format
- ✅ "Why It Works" explanations

### What's Missing (Opportunities)

| Gap | Market Demand | Effort |
|-----|--------------|--------|
| **Agent/Agentic Prompts** | 🔥🔥🔥 | Medium |
| **Claude 4.5 Specific** | 🔥🔥🔥 | Low |
| **Image Generation** | 🔥🔥 | Medium |
| **Sales & Marketing** | 🔥🔥 | Medium |
| **Multimodal (text+image)** | 🔥🔥 | Medium |
| **Self-Correcting Patterns** | 🔥🔥 | Low |
| **Meta-Prompting** | 🔥 | Low |

---

## 🚀 Recommended Additions

### Tier 1: High Impact, Low Effort (Add This Week)

#### 1. `techniques/xml-structured.md`
Claude 4.5's #1 technique - XML tags for structure
```xml
<task>Your task here</task>
<context>Background info</context>
<constraints>
- Constraint 1
- Constraint 2
</constraints>
<output_format>Expected format</output_format>
```

#### 2. `techniques/extended-thinking.md`
For complex reasoning (Claude's thinking mode)
```
Think through this step by step before answering.
Show your reasoning process, then provide the final answer.
```

#### 3. `techniques/self-correcting.md`
Built-in verification to reduce hallucinations
```
After generating your response:
1. Check each claim for accuracy
2. Flag anything you're uncertain about with [UNVERIFIED]
3. List assumptions you made
```

#### 4. `techniques/anti-botspeak.md`
Avoid phrases that scream "AI wrote this":
- Ban: "Here's the kicker", "Let's unpack", "That's rare", "quiet confidence"
- Include natural alternatives

#### 5. `techniques/permission-to-fail.md`
Reduce hallucinations by allowing uncertainty
```
If you're not sure, say so. I prefer "I don't know" 
over a confident wrong answer.
```

### Tier 2: High Impact, Medium Effort (Add This Month)

#### 6. `agents/orchestration-patterns.md`
Multi-agent coordination for complex tasks
```
You are the Coordinator. Break this task into subtasks:
1. Research Agent: Gather information
2. Analysis Agent: Evaluate findings  
3. Writer Agent: Draft output
4. Critic Agent: Review and improve
```

#### 7. `agents/plan-then-execute.md`
The pattern that reduces costs 90%
```
Phase 1 - Planning (no actions):
Create a detailed plan. Do not execute anything yet.

Phase 2 - Execution (after approval):
Execute the approved plan step by step.
```

#### 8. `agents/memory-management.md`
For agents that need persistent context
```
Before responding, check your memory:
- What do you know about this user/project?
- What decisions were made previously?
- What context is relevant?

After responding, update your memory with key facts.
```

#### 9. `sales/discovery-call.md`
Sales qualification framework
```
Act as a sales discovery expert. Ask questions to understand:
1. Current situation (pain points)
2. Impact of the problem
3. Decision process
4. Timeline and budget
Use SPIN selling methodology.
```

#### 10. `sales/objection-handling.md`
Handle common objections
```
Customer objection: "[OBJECTION]"
Product: "[PRODUCT]"

Respond using the Feel-Felt-Found method:
1. Acknowledge the concern
2. Share similar customer experience
3. Explain positive outcome
```

#### 11. `marketing/hook-generator.md`
Create attention-grabbing hooks
```
Create 10 hooks for: [TOPIC]
Use these patterns:
- Contrarian ("Stop doing X")
- Curiosity gap ("The hidden reason...")
- Social proof ("How [person] achieved...")
- Direct benefit ("Get [result] in [time]")
```

#### 12. `images/photo-realistic.md`
For DALL-E, Midjourney, etc.
```
[Subject] in [setting], [lighting type] lighting,
shot on [camera], [lens]mm lens, [style] style,
8k resolution, highly detailed, [mood] mood
```

#### 13. `images/style-transfer.md`
Consistent style across generations
```
Create an image in the style of [REFERENCE].
Key style elements to match:
- Color palette: [colors]
- Texture: [smooth/grainy/etc]
- Composition: [rule of thirds/centered/etc]
- Mood: [mood]
```

### Tier 3: Differentiation (Pro Tier Candidates)

#### 14. `patterns/critique-improve-loop.md`
```
Step 1: Generate initial response
Step 2: Critique your response - what's weak?
Step 3: Improve based on critique
Step 4: Final polished output
```

#### 15. `patterns/multi-perspective.md`
```
Analyze [TOPIC] from these perspectives:
1. Devil's Advocate: What could go wrong?
2. Optimist: What opportunities exist?
3. Pragmatist: What's realistic?
4. Expert: What do specialists know?

Synthesize into balanced recommendation.
```

#### 16. `patterns/constraint-based-creativity.md`
```
Generate [OUTPUT] with these constraints:
- Cannot use: [banned elements]
- Must include: [required elements]
- Budget: [limit]
- Time: [deadline]

Constraints force creative solutions.
```

#### 17. `workflows/research-to-report.md`
Multi-step research workflow:
```
Phase 1: Gather sources (list 10+ relevant sources)
Phase 2: Extract key findings (bullet points per source)
Phase 3: Identify patterns (what do sources agree/disagree on?)
Phase 4: Synthesize (coherent narrative)
Phase 5: Actionable insights (so what?)
```

---

## 📁 Proposed New Structure

```
ai-prompts/
├── techniques/          # Core prompting methods
│   ├── xml-structured.md      [NEW]
│   ├── extended-thinking.md   [NEW]
│   ├── self-correcting.md     [NEW]
│   ├── anti-botspeak.md       [NEW]
│   ├── permission-to-fail.md  [NEW]
│   └── ... (existing)
├── coding/              # Developer prompts
├── writing/             # Content creation
├── analysis/            # Data & research
├── research/            # Market & competitor
├── creative/            # Ideation & naming
├── agents/              # [NEW CATEGORY]
│   ├── orchestration-patterns.md
│   ├── plan-then-execute.md
│   └── memory-management.md
├── sales/               # [NEW CATEGORY]
│   ├── discovery-call.md
│   ├── objection-handling.md
│   └── cold-outreach.md
├── marketing/           # [NEW CATEGORY]
│   ├── hook-generator.md
│   ├── content-repurposing.md
│   └── ad-copy-framework.md
├── images/              # [NEW CATEGORY]
│   ├── photo-realistic.md
│   ├── style-transfer.md
│   └── product-photography.md
└── patterns/            # [NEW CATEGORY - Pro upsell]
    ├── critique-improve-loop.md
    ├── multi-perspective.md
    └── constraint-based-creativity.md
```

---

## 📈 Quick Wins for README

### Add "Claude 4.5 Compatibility" Badge
```markdown
[![Claude 4.5](https://img.shields.io/badge/Claude_4.5-Compatible-blueviolet.svg)](#)
```

### Add "2026 Updated" Section
Highlight what's new for 2026:
- XML structured prompts (Claude 4.5 optimized)
- Extended thinking patterns
- Anti-botspeak guidelines
- Agent orchestration

### Add "By AI Model" Quick Reference
| Prompt | Claude | GPT-4 | Gemini |
|--------|--------|-------|--------|
| XML Structured | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ |
| Extended Thinking | ⭐⭐⭐ | ⭐ | ⭐⭐ |
| Few-Shot | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |

---

## 🎯 Action Items

### This Week
- [ ] Add 5 Tier 1 techniques (low effort, high impact)
- [ ] Update README with 2026 badges
- [ ] Add model compatibility table

### This Month
- [ ] Create `agents/` category (3 prompts)
- [ ] Create `sales/` category (3 prompts)  
- [ ] Create `marketing/` category (3 prompts)
- [ ] Create `images/` category (3 prompts)
- [ ] Update prompt count badge

### For Pro Tier
- [ ] Move `patterns/` advanced prompts to pro
- [ ] Add multi-step workflows
- [ ] Add industry-specific prompts (SaaS, Agency, etc.)

---

## 📚 Research Sources

1. DreamHost - "5 Claude Techniques That Actually Work" (Dec 2025)
2. AIPromptsX - "Advanced Prompt Engineering" (Jan 2026)
3. The Neuron - "January 2026 Prompt Tips" 
4. Anthropic Docs - Claude 4.5 Best Practices
5. IBM - "2026 Guide to Prompt Engineering"
6. r/PromptEngineering - Community insights

---

*Plan created by Dan 🦞 - Ready to execute on your go*
