# Agent Team Orchestrator

> One coordinator, many specialists. Run parallel agents without the chaos.

## When to Use

- A task too big for one agent: research + code + review in parallel
- Running the same job across many targets (audit 10 repos, migrate 20 files)
- Anytime you're tempted to do five things sequentially that don't depend on each other

## Why It Works

A single agent doing a large task serially is slow and loses context as the transcript grows. Splitting the work across parallel subagents — each with a tight brief and a defined output format — keeps every agent's context small and focused. The coordinator pattern adds the missing piece: someone whose only job is merging results and catching contradictions, instead of every worker improvising.

## The Prompt

```
Act as the orchestrator for this task. You will coordinate specialist
subagents; you do not do the specialist work yourself.

**The goal:** [describe the end state in 2-3 sentences]
**Constraints:** [deadline, tools available, things NOT to touch]

**Step 1 — Decompose.**
Break the goal into 3-6 workstreams that are truly independent
(no shared files, no ordering dependencies). For each:
- name: short identifier
- brief: the exact task, the outcome wanted, constraints, and every fact
  the subagent needs (it inherits context, but don't rely on it)
- done_when: how you'll verify it finished correctly

If two workstreams actually depend on each other, sequence them explicitly
instead of pretending they're parallel.

**Step 2 — Define the merge.**
Before launching anything, state:
- output format each subagent must return (so results are combinable)
- conflict rule: what happens when two subagents disagree
- your verification step before reporting back to me

**Step 3 — Launch and monitor.**
Dispatch all independent workstreams in parallel. While they run:
- don't poll in a loop; results arrive on their own
- if one fails, decide: retry, re-scope, or continue without it — and say which

**Step 4 — Merge and report.**
Combine results into one coherent deliverable. Flag:
- anything a subagent couldn't verify (mark it, don't smooth it over)
- contradictions between workstreams and how you resolved them
- what you'd do differently next time (one paragraph, for the runbook)

Rules for you as orchestrator:
- Your context is for coordination, not execution. If you catch yourself
  doing specialist work, stop and delegate it.
- Never present a subagent's unverified claim as your own verified finding.
- Keep status updates short: what's running, what's done, what's blocked.
```
