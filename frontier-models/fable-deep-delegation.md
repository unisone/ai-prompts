# Fable Deep Delegation

> Claude Fable 5.1 can carry a workstream for hours — implementation through the review tail. Give it a brief worthy of that stamina.

## When to Use

- Large refactors or repo migrations you want to delegate, not supervise line-by-line
- Multi-hour autonomous coding sessions with Claude Fable 5.1
- Any task where the model should run, verify, self-review, and report back

## Why It Works

Long autonomous runs fail on vague delegation, not model capability: no verifiable definition of done, no boundaries (drift compounds over hours), no checkpoints (you discover problems at hour four instead of hour one). A four-part brief — mission, boundaries, checkpoints, verification — converts Fable 5.1's stamina into completed work instead of impressive wandering.

## The Prompt

```
I want to delegate a long-running coding workstream to Claude Fable 5.1.
Interview me, then write the delegation brief.

**Context:** [repo, stack, what the workstream is]

**Step 1 — Interview me (one question at a time, max 8 questions).**
Ask about: the real goal, what "done" looks like in verifiable terms,
files/systems that are off-limits, existing tests or verification commands,
branch and merge expectations, and anything that's burned us before in
this codebase.

**Step 2 — Write the delegation brief** with these four sections:

1. **Mission** — done-criteria as verifiable facts
   ("all 40 existing tests pass; new tests cover token refresh"),
   never adjectives ("improve", "clean up").

2. **Boundaries** — explicit do-not-touch list: files, APIs, behaviors.
   Assume the model will drift over a long run; boundaries contain it.

3. **Checkpoints** — stop-and-report gates: after planning, after
   implementation, before any merge. What I approve at each gate.

4. **Verification** — the exact commands that prove success
   (npm test, cargo test, pytest). The model runs them after the FINAL
   edit, not before — last-minute fixes break things.

**Step 3 — Effort recommendation.**
Recommend low / medium / high effort for this workstream and justify it.
Default to medium; only recommend high if the problem is genuinely hard,
and note that extra-high effort has been observed to degrade writing
quality — keep docs and prose tasks at medium.

**Step 4 — Review-tail protocol.**
Specify how the model self-reviews (PR-description summary of its own
changes, then a reviewer pass over the diff), and state the merge rule:
autonomous merge only for scratch branches; production branches keep a
human merge gate.

**Step 5 — Kill criteria.**
When should I intervene? Define the signals of a stuck run (same failing
approach retried, checkpoint missed, scope expanding) and what I do
in each case.

Output the brief as markdown I can paste into the session.
```
