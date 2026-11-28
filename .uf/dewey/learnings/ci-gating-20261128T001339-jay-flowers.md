---
tag: ci-gating
author: jay-flowers
category: gotcha
created_at: 2026-11-28T00:13:39Z
identity: ci-gating-20261128T001339-jay-flowers
tier: draft
as_of: "containerfile@a74bf2fcb20fa4013c687f684228a3c520b78638"
---

A required-check migration split between a repo workflow and org-level safe-settings must land the org-side configuration first or atomically — otherwise skipped builds leave old inner checks pending forever and the chore PRs the change targets become unmergeable.
