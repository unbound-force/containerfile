---
tag: github-actions
author: jay-flowers
category: reference
created_at: 2026-11-28T00:13:40Z
identity: github-actions-20261128T001340-jay-flowers
tier: draft
as_of: "containerfile@a74bf2fcb20fa4013c687f684228a3c520b78638"
---

A GitHub Actions reusable-workflow caller job's result aggregates its inner jobs, so an aggregate gate needing only the caller's result transitively covers inner steps like multi-arch manifest pushes.
