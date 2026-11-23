# Documentation standard

The shared standard for human documentation published on docs.unset.sh. The metadata proposal below remains
pending renderer support; the writing and review rules apply independently of that tooling.

## Purpose and audience

Help readers form an accurate mental model, accomplish useful work, and understand how the code fits together. Give newcomers a route into the project and experienced contributors a route to precise detail.

Every page answers a recognisable question or supports a clear outcome. Start with that answer or outcome. State the assumed knowledge when it affects whether the reader can follow the page.

Public documentation under this standard covers current organisation projects. Internal agent handoffs, work logs, unresolved implementation plans, and the legacy app mirror are not learning material. A relevant accepted decision can support an explanation; a decision archive does not replace it. Publishing the organisation's full decision archive remains a separate decision.

## Two routes, one source

Offer **Learn and use** and **Understand and contribute** with equal prominence. A page may serve both routes. Link to it from both rather than maintaining two versions.

Repository overviews explain what the project does, what it owns, what it depends on, and where to begin. Deeper navigation follows readers' questions rather than reproducing the filesystem. Create only populated sections; do not create empty tutorial or reference categories for symmetry.

## Page formats

The four core learning formats follow [Diátaxis](https://diataxis.fr/); an overview supplies the entry point.

| Format | Reader's question | Required shape |
| --- | --- | --- |
| Overview | What is this, and where should I go? | Purpose, place in the system, two reader routes, useful links |
| Tutorial | Can you teach me through a first success? | Outcome, prerequisites, guided exercise, expected result, next step |
| Guide | How do I complete this task? | Goal, prerequisites, ordered actions, verification, relevant recovery |
| Explanation | How does this work, and why? | Mental model, focused visual when useful, worked example, trade-offs, sources |
| Reference | What exactly is supported? | Precise contract, constraints, examples, errors, version, source |

Architecture and code walkthroughs are explanation pages. Troubleshooting is normally a guide organised around an observable symptom. Contributor setup is a guide. Choose the primary purpose; link to other formats instead of turning every page into all of them.

## Explanation and example

Keep these visibly distinct, adjacent, and connected:

1. **Explanation:** describe the idea and why the reader needs it.
2. **Visual:** show the relevant relationship, boundary, sequence, or state change when that clarifies the idea.
3. **Worked example:** follow one concrete input through the behaviour.
4. **What happened:** explain the result and a meaningful limit or failure case.
5. **Go deeper:** link to exact reference, implementation, and authoritative specifications.

Use descriptive headings such as “How records are validated” and “Example: a missing required field”. These are content patterns, not five mandatory headings on every page. A simple fact needs neither a diagram nor an exercise.

Keep the same names and values throughout the prose, diagram, code, expected output, and source links. Label invented examples as illustrative. Do not imply an example schema, endpoint, command, or module exists in unset.sh unless it does.

## Writing and editing

- Write for people. Use active voice, direct verbs, and “you” for the reader. Name the component that performs an action.
- Use sentence-case headings. Task titles begin with the action; explanation titles name the concept or question.
- Define unfamiliar terms and expand abbreviations at first use. Explain the mechanism before depending on its jargon.
- Use short, connected paragraphs. Keep enough detail to explain causes and consequences. Split a page when its reader goal changes, not at an arbitrary word count.
- Remove repetition, marketing claims, filler introductions, and conclusions that merely repeat the page. Avoid “just”, “simply”, “obviously”, and promises such as “secure” without explaining the property and evidence.
- Prefer prose for reasoning, numbered steps for sequences, bullets for parallel items, and tables for comparable facts. Avoid a page made entirely of fragmented bullets.
- Use the organisation's established spelling: “colour”, “behaviour”, and “licence” as a noun. Preserve exact API, command, file, and UI spellings.
- Put code identifiers in backticks and visible UI labels in bold. Use descriptive link text rather than “here”.
- Put conditions and consequences before the step they affect. Keep essential prerequisites and safety information visible.

For example:

| Avoid | Prefer |
| --- | --- |
| Simply leverage the schema to seamlessly validate your data. | Validate the record against its schema before submitting it. |
| The data is processed by the service. | The validator checks the record's required fields and types. |
| This module handles identity. | This module resolves account identifiers. Session creation belongs to the interface layer. |

The last two examples illustrate writing style, not claims about a particular implementation.

## Code and examples

State the working directory, required version, and prerequisites before a runnable example. Use the command the repository actually supports. Explain registry authentication or other setup when required; do not present a package command as universally runnable.

Use fenced code with a language label. Keep code as selectable text. Copyable command blocks contain commands only: no shell prompt, line numbers, or unrelated output. Put expected output in a separate block and identify variable portions. Use explicit placeholder names and explain how to replace them; never include real credentials or personal data.

Give examples a useful starting state and an observable result. Include a failure example when it teaches a constraint or boundary. A minimal excerpt must say what it omits and link to the complete source. Do not label pseudocode as executable code.

For runnable examples, verify them against the version documented and record that evidence in the source PR. Prefer repository-owned fixtures or generated excerpts when duplication would otherwise drift. If an example was not executed, say how it was checked and do not claim it runs.

## Visual explanations

Use visuals regularly where they improve understanding:

| Need | Suitable visual |
| --- | --- |
| Place a project in the ecosystem | Context map |
| Explain ownership and modularity | Boundary and dependency diagram |
| Follow one operation | Sequence or numbered flow |
| Explain state or transformation | Before/after view or state diagram |
| Connect code to behaviour | Short annotated excerpt with matching steps |

Each diagram answers one question. Give it a title and a stated scope. Use recognisable names, labelled arrows, and a legend for non-obvious notation. Say whether arrows represent imports, calls, or data movement. Do not mix these meanings silently.

A caption explains the takeaway. Adjacent text provides the essential information for people who cannot see the diagram. Never rely on colour alone. Keep labels readable in both themes and on narrow screens; split a dense diagram into levels instead of shrinking it.

Commit editable diagram source with its rendered asset. Serve assets locally. The initial website uses static diagrams; a proposed interactive explanation must improve learning, work by keyboard, preserve a useful static reading, and use a shared site component. No per-page scripts or remote embeds.

Screenshots are appropriate for recognising a UI state. They are not a substitute for code, a structural diagram, or text that readers need to search and copy.

## Sources and truth

Distinguish these kinds of claim:

| Claim | Supporting evidence |
| --- | --- |
| “The protocol requires…” | The relevant official specification and section |
| “unset.sh does…” | Current implementation, schema, and relevant tests |
| “The design intends…” | An accepted decision, with implementation status stated separately |
| “This example illustrates…” | A clearly labelled example; do not present it as deployed behaviour |

Explain the relevant rule locally, then link to its authoritative source near the claim. Prefer official AT Protocol specifications over a third-party summary. Use a friendly upstream guide for additional learning and the specification for normative details. Do not copy large upstream explanations into unset docs.

Code walkthroughs link to the exact commit and relevant file or symbol they describe. General navigation may link to the current source tree. Record the checked revision/version in the source page or its generation metadata; never invent a commit. Keep API reference tied to an identified release, schema revision, or explicitly labelled unreleased `main` state. “Latest” alone is insufficient.

Current and planned architecture must have separate, explicit labels. Accepted decisions explain intent and trade-offs; they do not prove the implementation already matches. Document a material discrepancy rather than drawing the desired architecture as though it exists.

## Workflow explanations

Explain workflows as observable processes, not lists of configuration keys. Name the trigger, responsible repository and owner, inputs and prerequisites, ordered steps, outputs and destinations, and meaningful failure and recovery paths. Distinguish who owns the process from the identity that executes it.

Link the workflow files and supporting scripts at the checked revision. State which behaviour is running today and put proposed changes in a separate section. Explain permissions, approvals, and trust boundaries where they affect what the workflow can do; never include secret values.

Follow one concrete run from trigger to result, then a useful failure case. Identify the evidence used to check the explanation: code review, a test, or an observed run. A successful run alone does not prove every recovery path works. Use the [workflow template](templates.md) when helpful.

## Source format

Use UTF-8 Markdown with YAML front matter. Keep the body readable on GitHub as well as the website. Use one title from front matter; body headings begin at level two. Do not skip levels. Use lowercase hyphenated paths and keep published paths stable.

Proposed minimum metadata: `title`, `description`, `weight`, and `params.doc_kind`. The latter is one of `overview`, `tutorial`, `guide`, `explanation`, or `reference`. Hugo's `type` remains `docs`; it is a rendering selector, not the editorial format. This schema is a proposal, not an existing CI check. See [templates](templates.md).

Use relative `.md` links within exported content. Use canonical documentation URLs for other repository sections and absolute GitHub links for source files outside the exported tree. Check both source and rendered destinations, including fragments. Preserve a tested redirect or equivalent supported path when moving a published page.

Use standard Markdown first. No raw HTML, inline styles/scripts, remote resources, or unapproved shortcodes. Local images belong beside the page in a supported page bundle. Retain asset attribution and source licences.

## Maintenance and review

When code, behaviour, workflows, or ownership changes, include the related documentation update in the same pull request, or record an explicit reason for review that the existing documentation remains correct. Identify the affected pages and how they were checked. An ownership move also updates the canonical `repos.json` in `unset-sh/.github` and its generated map, rather than only a downstream explanation.

Reviewers check understanding as well as factual accuracy: can a new reader explain the responsibility, follow the example, and find the source? Automated impact and drift checks can flag missing updates or changed inputs; they cannot establish that an explanation still means the right thing.

Never edit generated reference or mirrored documentation by hand. Edit the source or generator and regenerate. Export only the repository's selected public documentation and its own section. Do not infer that every Markdown file should be published.

Keep the checked source revision and export provenance with the documentation or generation metadata. A new export timestamp alone is not evidence of a content review. The owning repository sets a review interval and responsible maintainer in its local contribution instructions; at that interval, recheck examples, source links, workflow behaviour, and ownership against current sources, and record the result. Report unavailable verification rather than updating freshness claims blindly.

Before publication, check the page's purpose, correctness, example, source links, diagram readability, heading structure, and relevant version. Mechanical checks can enforce paths, links, metadata, and rendering. A word count or a readability score cannot establish that a technical explanation is good.
