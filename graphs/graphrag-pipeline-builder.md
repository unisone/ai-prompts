# GraphRAG Pipeline Builder

> Vector search finds similar chunks. GraphRAG follows connections. Plan the pipeline before you extract.

## When to Use

- Questions need multi-hop reasoning ("what caused X, and who was involved?")
- Plain RAG returns chunks that never quite connect
- Building queryable knowledge from unstructured documents
- Deciding whether you need GraphRAG at all (sometimes you don't)

## Why It Works

GraphRAG projects fail in predictable ways: no schema (extraction chaos), chunks too large (dropped relationships), no dedup (three nodes for one person), and no spot-check loop (silent error compounding). Walking through pipeline decisions explicitly — schema, chunking, extraction, storage, query patterns — surfaces these failure modes while they're still design choices, not production bugs.

## The Prompt

```
Help me plan a GraphRAG pipeline. Be skeptical: talk me out of it if plain
vector RAG would do.

**Documents:** [what and how many — e.g., "2,000 support tickets", "500 PDFs"]
**Questions it must answer:** [3-5 real questions]
**Scale:** [prototype / team tool / production]
**Constraints:** [infra limits, budget, latency needs]

**Step 1 — The skeptic's gate.**
For each of my questions: could it be answered by vector search over
well-chunked text? If yes to all, say so and stop — recommend plain RAG.
Only continue if at least one question genuinely needs relationship traversal.

**Step 2 — Schema.**
Propose node types (5-10) and edge types with direction. Every type must map
to one of my questions. Include dedup/normalization rules.

**Step 3 — Chunking and extraction.**
Recommend chunk size (default 500-1000 tokens with overlap) and write the
entity/relation extraction prompt: allowed types, normalization rules,
JSON output format. Include a spot-check plan (how many chunks to verify
by hand, what error rate is acceptable).

**Step 4 — Storage.**
Recommend Kuzu (embedded, prototype/small team) vs Neo4j (multi-user, large
graphs). Output the Cypher DDL for the schema.

**Step 5 — Query patterns.**
For each of my questions, write the Cypher query that answers it, and show
the agent loop: question → Cypher → rows → LLM synthesis with citations.
Include the rule: if a query returns nothing, reformulate — never hallucinate
graph content.

**Step 6 — Build order.**
Numbered checklist from empty repo to working pipeline, each step verifiable.
Mark which steps need my input (schema approval, spot-checks) vs which an
agent can do autonomously.

Output as markdown I can hand to a coding agent.
```
