---
tag: github-actions
author: jay-flowers
category: pattern
created_at: 2026-11-28T00:13:35Z
identity: github-actions-20261128T001335-jay-flowers
tier: draft
as_of: "containerfile@a74bf2fcb20fa4013c687f684228a3c520b78638"
---

A gated job's `if: !cancelled() && (github.event_name != 'pull_request' || gate-output)` keeps push/tag builds running even when the gate job fails, so constitutionally required push builds cannot be blocked by gate infrastructure failures.
