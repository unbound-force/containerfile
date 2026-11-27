---
tag: review-dispatch
author: jay-flowers
category: gotcha
created_at: 2026-11-25T22:37:25Z
identity: review-dispatch-20261125T223725-jay-flowers
tier: draft
as_of: "containerfile@a43d7efe41dad8781e50de7f832e345c0c07e9e5"
evidence:
  - "session:ses_deb2cef96ffeClu2J4YCpTOg7W"
  - "dewey:.opencode/agents/divisor-adversary.md"
---

In the containerfile repo environment, all divisor-* agent definitions pin model `google-vertex-anthropic/claude-opus-4-6@default`, which is not a configured provider — dispatching them via the task tool fails with "Model not found" for every persona. Editing the agent files does not help: the agent registry (and pinned model) is cached at session start. Working fallback for /uf.review-pr and /uf.review-council dispatch: run each persona through the `general` subagent type with the persona contract fully inlined (Step 0 = read .opencode/agents/divisor-<name>.md and adopt the role, persona focus, frozen PR metadata, inlined diff, rules, structured response contract) and record the actual runtime model in the dispatch provenance table for transparency. Probe with a trivial general-agent dispatch first to confirm viability.
