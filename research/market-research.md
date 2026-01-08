# Market Research Deep Dive

## Description

Structured prompt for comprehensive market research. Produces actionable insights, not generic overviews.

## When to Use

- Evaluating a new market opportunity
- Understanding competitive landscape
- Preparing for investor conversations
- Go-to-market planning

## Prompt

```
Conduct market research for: [PRODUCT/SERVICE]

<research_framework>
## 1. Market Definition
- What problem does this solve?
- Who has this problem most acutely?
- How are they solving it today?

## 2. Market Sizing
- TAM: Total addressable market (everyone who could use this)
- SAM: Serviceable addressable market (who you can realistically reach)
- SOM: Serviceable obtainable market (realistic 3-year capture)
- Show your math with sources

## 3. Customer Segments
For each segment:
- Demographics/firmographics
- Pain points (ranked by severity)
- Current solutions and spend
- Willingness to switch

## 4. Competitive Landscape
| Competitor | Positioning | Strengths | Weaknesses | Pricing |
Create this table for top 5-7 players

## 5. Market Dynamics
- Key trends (with evidence)
- Regulatory factors
- Technology shifts
- Timing considerations (why now?)

## 6. Go-to-Market Insights
- Best acquisition channels for this market
- Typical sales cycle length
- Key objections and how to overcome
- Pricing expectations

## 7. Risks & Unknowns
- What could kill this market?
- What assumptions need validation?
- Key metrics to watch
</research_framework>

<output_requirements>
- Cite sources where possible (even if knowledge cutoff applies)
- Quantify claims ("growing market" → "14% CAGR 2023-2028")
- Flag low-confidence assertions
- Be direct about what you don't know
</output_requirements>
```

## Why It Works

1. **Structured framework**: Prevents rambling, ensures coverage
2. **Sizing math**: Forces specificity over hand-waving
3. **Competitor table**: Easy to scan, update, share
4. **Risk section**: Balances optimism with realism

## Example

Input: "Conduct market research for: AI-powered code review tool"

Output includes:
- TAM: $XX billion developer tools market
- SAM: Teams >10 engineers with CI/CD pipelines
- Competitor matrix (GitHub Copilot, Codacy, SonarQube, etc.)
- Trend analysis (AI adoption, shift-left security)
- Risk: GitHub bundling, open-source alternatives

## Notes

- Best with web search enabled for current data
- Combine with competitor-analysis.md for deeper competitive view
- Follow up with customer interviews to validate
