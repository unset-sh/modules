---
name: org-documentation
description: Use when creating, materially changing, or reviewing human documentation in an unset.sh repository, including tutorials, task guides, reference pages, architecture and workflow explanations, code walkthroughs, and documentation adoption.
---

# Human documentation

Help people learn and use a project, and understand its code well enough to contribute. These are equal
reader needs. Write in the repository that owns the behaviour; the website renders its selected public pages.

## Read for the task

| Task | Read |
| --- | --- |
| Write or review a public page | [Standard](standard.md) and the relevant [page template](templates.md) |
| Explain architecture, modularity, or a code path | [Architecture](architecture.md), then its template |
| Explain a workflow or review documentation freshness | [Standard](standard.md), then the workflow template or repository facts |
| Adopt the standard or configure a source repository | [Repository facts and adoption](repository-rules.md) |

Apply the standard to the page's actual reader goal. Keep explanation, worked example, and observed result
distinct. Use a visual when it clarifies a relationship or boundary. Link claims to verified code and official
specifications; distinguish current behaviour, illustrative examples, and planned work.

The site's publication scope is organisation repositories only. The app's future documentation is a content
plan in the architecture guide, not permission to restore the old app mirror or add empty navigation.

The proposed renderer metadata is explicitly marked in the standard and templates. Do not claim those fields,
components, or checks are implemented until the owning renderer supports them. Use the source repository's
documented paths and checks; do not invent them or modify the installed kit copy.
