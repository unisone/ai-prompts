# Cypher Query Assistant

> Write Cypher that actually runs. From pattern matching to multi-hop traversals, with debugging built in.

## When to Use

- Learning Cypher (Neo4j / Kuzu query language)
- A query returns nothing and you don't know why
- Translating a question into a graph traversal
- Optimizing a slow traversal

## Why It Works

Cypher reads like ASCII art, which makes it deceptively easy to write queries that are syntactically valid but semantically wrong — especially around direction, variable-length paths, and null handling. The debug loop below (explain the pattern in words first, then verify each hop returns rows) catches the most common failure: a traversal that's correct in your head but empty in the database.

## The Prompt

```
Help me write a Cypher query. Work in the open so I learn the pattern.

**My graph:** [node labels and relationship types, e.g. "(:Person)-[:WORKS_ON]->(:Project)"]
**The question:** [what I want to find, in plain English]
**My attempt (optional):** [paste it if you have one]

**Step 1 — Say it in words.**
Describe the traversal as a sentence: "start at all Person nodes, follow
WORKS_ON edges to Projects, keep the ones whose status is 'active'."
If you can't say it in one sentence, the query is trying to do too much —
split it.

**Step 2 — Write the query.**
```cypher
[your query here, formatted with one clause per line]
```

**Step 3 — Debug checklist.**
Walk me through verifying it:
- Direction check: does each arrow point the way the data was loaded?
- Label check: exact label spelling and case?
- Hop-by-hop: run each MATCH alone — which hop returns zero rows?
- Null traps: OPTIONAL MATCH vs MATCH — am I accidentally filtering?
- Variable-length paths: is the upper bound sane? (unbounded *.. traversals
  on dense graphs explode)

**Step 4 — Common patterns cheat sheet.**
Give me the 5 patterns I'll reuse most, adapted to MY schema:
1. Find neighbors: MATCH (a:Label {prop: $v})-[r]-(b) RETURN ...
2. Multi-hop: MATCH (a)-[:REL1]->(b)-[:REL2]->(c)
3. Shortest path: MATCH p = shortestPath((a)-[*]-(b))
4. Aggregation: MATCH (a)-[r]->(b) RETURN a, count(r) ORDER BY count(r) DESC
5. "Not connected": MATCH (a) WHERE NOT (a)-[:REL]-(:Label) RETURN a

**Step 5 — Performance note.**
Flag anything in my query that won't scale (cartesian products from
comma-separated MATCHes, unbounded traversals, missing index on the
lookup property) and show the fix.

If my question can't be answered with the schema I described, say so and
tell me what edge or property is missing — don't invent a query against
data that isn't there.
```
