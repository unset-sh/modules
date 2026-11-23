# Page templates

Copy the relevant Markdown shape into the owning repository, replace every `TODO`, and remove `draft: true`
only when the page is ready. These are authoring templates, not pages to export unchanged.

The examples show the proposed metadata: `title`, `description`, `weight`, and `params.doc_kind`. The renderer
has not yet enforced this schema or implemented routing by `doc_kind`; do not claim otherwise. Preserve the
existing `type: docs` and cascade on the exported section index. Editorial format belongs in `params.doc_kind`,
not Hugo's reserved `type` field. See [Hugo front matter](https://gohugo.io/content-management/front-matter/).

## Repository section

The section's `menus.main.weight` preserves the existing export contract; coordinate a value through the site's established ordering. The sample value is illustrative.

````markdown
---
title: "TODO: Project name"
description: "TODO: What this project helps people do or understand."
weight: 30
type: docs
cascade:
  type: docs
menus:
  main:
    weight: 30
params:
  doc_kind: overview
draft: true
---

TODO: Explain the purpose in one short paragraph.

## Where it fits

TODO: Name its responsibility, important boundary, and relevant dependencies.

## Learn and use

TODO: Link the first exercise, common tasks, and shared reference.

## Understand and contribute

TODO: Link architecture, a code walkthrough, and the contribution guide.

## Source

TODO: Link the repository and relevant version or release information.
````

For each following body, prepend this metadata, changing the kind and title:

```yaml
---
title: "TODO: Reader's question or action"
description: "TODO: The outcome or concept this page explains."
weight: 10
params:
  doc_kind: explanation
draft: true
---
```

## Tutorial body

```markdown
TODO: State what the reader will build or observe in this exercise.

## Before you start

TODO: Name assumed knowledge, exact setup, versions, and working directory.

## Build the first example

TODO: Give numbered steps. Explain each new idea at the point it becomes useful.
TODO: Use a small visual if the behaviour would otherwise be difficult to picture.

## Check the result

TODO: Show the expected result and explain why it happened.

## What you learned

TODO: Connect the observed result to the concept, without repeating the procedure.

## Next step

TODO: Link a useful task or deeper explanation and the relevant reference.
```

## Guide body

```markdown
TODO: State the task and when to use this procedure.

## Before you start

TODO: Name prerequisites, scope, working directory, and relevant consequences.

## Complete the task

TODO: Give numbered actions with copyable commands or precise UI labels.

## Verify the result

TODO: Give an observable success check.

## If it fails

TODO: Explain meaningful failure symptoms, recovery, and reversal where applicable.
TODO: Omit this heading if it adds no useful information.
```

## Explanation body

```markdown
TODO: Answer the main question and connect it to a reader need.

## How it works

TODO: Explain the mental model. Define unfamiliar terms.
TODO: Add a focused diagram, caption, and textual equivalent where useful.

## Example: TODO concrete scenario

TODO: Show a small, consistent input and what happens to it.

## What the result means

TODO: Explain the outcome and one relevant constraint or failure case.

## Why it works this way

TODO: Explain a meaningful trade-off. Link an accepted decision if relevant.

## Go deeper

TODO: Link precise reference, verified implementation, and official specifications.
```

## Reference body

```markdown
TODO: Identify the interface/schema and the version or source revision described.

## Contract

TODO: Describe inputs, outputs, defaults, required fields, and constraints.
TODO: Use a table only where its rows are genuinely comparable.

## Example

TODO: Give a minimal valid example and its result.

## Errors and edge cases

TODO: Identify observable failures and relevant limits without inventing behaviour.

## Source

TODO: Link the canonical schema/API implementation and governing specification.
```

## Architecture body

```markdown
TODO: State the system/module scope and checked revision or release.
TODO: Label current behaviour; put any target design in a separate named section.

## Where it fits

TODO: Show the context and external dependencies at one clear level.

## Responsibilities and boundaries

TODO: Show the important modules. State what each owns and does not own.
TODO: Name each boundary as logical, package, process/network, or trust where relevant.

## Allowed dependencies

TODO: Show and explain the allowed direction, important forbidden edge, and real enforcement.

## Example: TODO an operation through the system

TODO: Trace one input through the contracts with a numbered sequence diagram.
TODO: Link each important step to code at the checked revision.
TODO: Show a significant failure path and the component responsible for it.

## Changing this behaviour

TODO: Explain where a realistic change belongs and how to verify it.

## Decisions and sources

TODO: Link governing specifications, relevant decisions, contracts, and checks.
```

## Workflow explanation body

```markdown
TODO: State the workflow's purpose and the source revision checked.
TODO: Label current behaviour; separate any proposed changes from it.

## Trigger and ownership

TODO: Name the event or schedule, responsible repository and maintainer, and executing identity.

## Inputs and boundaries

TODO: State inputs, prerequisites, permissions and approvals that affect the run.
TODO: Name secret requirements without giving their values.

## Example: TODO one run

TODO: Follow one concrete input through ordered steps to its observable outputs and destinations.
TODO: Use a sequence diagram where useful, with the same names as the prose and source.

## Failure and recovery

TODO: Show a meaningful failure, who can act, and the supported recovery or retry.
TODO: State any recovery behaviour that has not been verified.

## Source and verification

TODO: Link the workflow files and supporting scripts at the checked revision.
TODO: Identify the tests, source review or observed run used to verify this explanation.
TODO: Link the owning repository's documentation-review responsibility and interval.
```
