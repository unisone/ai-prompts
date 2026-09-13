# Knowledge Graph Schema Designer

> A queryable graph starts with a disciplined schema. Design the types before you extract a single entity.

## When to Use

- Starting a knowledge graph or GraphRAG project
- Your extraction produces 40 spellings of the same relationship
- Queries keep coming back empty because the schema doesn't match the questions
- Reviewing someone else's graph design before implementation

## Why It Works

Most failed knowledge graphs fail at schema design, not extraction: too many node types, vague edge names, no normalization rules. Forcing the schema to be justified against real queries — "show me the question this edge type answers" — kills speculative types early, when they're still cheap to remove.

## The Prompt

```
Help me design a knowledge graph schema for this domain.

**Domain:** [e.g., "internal engineering docs", "customer support tickets", "research papers on batteries"]
**Source material:** [what documents feed the graph]
**Key questions the graph must answer:** [list 5-8 real questions, e.g. "which services depend on the payments API?"]

**Step 1 — Propose node types (5-10 max).**
For each: name, 2-4 properties with types, and which question(s) it serves.
If a node type serves no listed question, cut it.

**Step 2 — Propose edge types.**
For each: name (VERB_PHRASE, e.g. DEPENDS_ON), direction (A→B), properties,
and the question it answers. Ban vague edges like RELATED_TO or ASSOCIATED_WITH —
every edge must earn its specificity.

**Step 3 — Normalization rules.**
How do we keep "J. Smith", "John Smith", and "Smith" as one node?
Propose dedup keys and merge rules per node type.

**Step 4 — Temporal modeling.**
Which facts change over time? (roles, statuses, ownership) Show how to model
them with validity timestamps instead of overwriting.

**Step 5 — Schema as Cypher DDL.**
Output the full schema as CREATE NODE TABLE / CREATE REL TABLE statements
(Kuzu/Neo4j Cypher dialect), plus 3 sample queries that answer 3 of my key
questions — proving the schema actually serves them.

Challenge me: flag any question from my list the schema CAN'T answer, and
tell me what's missing.
```
