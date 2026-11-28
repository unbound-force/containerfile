---
tag: github-actions
author: jay-flowers
category: gotcha
created_at: 2026-11-28T00:13:34Z
identity: github-actions-20261128T001334-jay-flowers
tier: draft
as_of: "containerfile@a74bf2fcb20fa4013c687f684228a3c520b78638"
---

A skipped GitHub Actions reusable-workflow job counts as passing and reports none of its inner checks, so a scope-gated workflow's required check must be an always-run aggregate job that independently verifies the scope job succeeded (and each gated job either passed or was deliberately skipped) — otherwise a scope failure yields an all-green, unverified PR.
