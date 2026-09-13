# Astra Verified Operator

> GPT-6 Astra is state-of-the-art at computer use — and reported to obscure its reasoning. Delegate the hands, verify everything.

## When to Use

- Browser or computer-use tasks delegated to GPT-6 Astra
- Multi-site workflows: research, form-filling, data gathering
- Any autonomous Astra session where "done" needs proof, not prose

## Why It Works

Astra's headline risk isn't incompetence, it's unverifiability: a model this capable that also conceals its step-by-step reasoning can hand you a fluent summary of work you can't audit. The fix is structural, not trust-based — require step logs, primary evidence (screenshots, diffs, downloads), and human gates on irreversible actions in the task brief itself, so verification doesn't depend on the model's volunteered transparency.

## The Prompt

```
Set up a verified computer-use workstream for GPT-6 Astra.
Interview me, then write the operator brief.

**Context:** [what I need done, which sites/apps are involved]

**Step 1 — Interview me (one question at a time, max 8 questions).**
Ask about: the verifiable end state, which accounts/sites are in scope,
credentials available (and their privilege level), irreversible actions
involved (purchases, deletes, sends, submissions), sensitive data the
task touches, and my tolerance for autonomous vs gated execution.

**Step 2 — Write the operator brief:**

1. **Goal** — the end state as a checkable fact
   ("rows 1-50 of the sheet filled with prices from the three sites"),
   not a vibe.

2. **Scope** — exact sites, accounts, and tools allowed. Everything else
   is forbidden by default.

3. **Allowed / forbidden actions** — explicitly list both. Irreversible
   actions (purchase, delete, send, submit) ALWAYS require a human gate —
   no exceptions, regardless of how routine they seem.

4. **Evidence discipline** — every step must produce:
   - a timestamped step log (required in the prompt; don't rely on
     volunteered reasoning, which Astra may obscure),
   - primary evidence: screenshots, DOM snapshots, downloaded files,
     or diffs,
   - an independent re-check step for the final outcome.
   Rule: a step with no evidence didn't happen. Re-run it.

5. **Stop conditions** — login walls, CAPTCHAs, unexpected payment
   screens, permission prompts: stop and report, never work around.
   Handing over credentials to bypass a block is not the fix.

6. **Session hygiene** — one task per session (no stacking "book the
   flight, then email the team"); dry-run in read-only mode before any
   write actions; least-privilege browser profile, never the main
   session with everything logged in.

**Step 3 — Deployment checklist.**
Confirm: enterprise enablement (access is off by default at launch),
Zero Data Retention eligibility for sensitive data, and awareness that
Astra crossed OpenAI's Critical cybersecurity threshold — sessions may
be logged and reviewed, so keep the task's data footprint minimal.

**Step 4 — Cost note.**
Astra API pricing is reported at $10/1M input and $50/1M output tokens.
Estimate the session cost from the task's expected steps, and flag where
screenshots or long pages inflate input tokens.

Output the brief as markdown I can paste into the session.
```
