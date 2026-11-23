# Architecture that readers can follow

An explanation format within the [documentation standard](standard.md).

An architecture page succeeds when a reader can explain where a change belongs, which boundary it crosses, and why that boundary exists. A directory tree alone does not explain architecture.

## Start with context, then zoom in

Use the [C4 model's levels](https://c4model.com/diagrams) as a guide, not a quota. Begin with the project and its external dependencies. Show applications and data stores next where relevant. Explain internal modules only when their separation matters. Do not draw every class or function.

Each view states what it represents: a deployed process, logical module, source package, or external service. A repository, process, and module are different boundaries; draw and label them accordingly.

## Describe each important boundary

| Question | What the page must make clear |
| --- | --- |
| What does it own? | Responsibility, decisions, and data it controls |
| What does it not own? | Adjacent responsibility and its actual owner |
| How is it reached? | Public interface, exported function, message, or HTTP contract |
| What crosses it? | Inputs, outputs, errors, identity/context, and relevant data |
| What may it depend on? | Allowed dependency direction and reason |
| What must it not depend on? | The meaningful forbidden dependency or bypass |
| Where is it implemented? | Relevant module entry point, contract, and implementation |
| What keeps it true? | A real guard, test, type boundary, review rule, or an explicit enforcement gap |

Do not call a boundary enforced unless the linked evidence supports that claim. A diagram's arrow is not an enforcement mechanism.

## Separate structure from runtime

A dependency diagram answers “what is allowed to import or depend on what?”. A runtime flow answers “what happens when this operation runs?”. They can have different arrow directions. Label them separately.

For each important operation, trace one concrete example:

1. Name the trigger, starting state, and expected result.
2. Follow the request or data through the responsible modules.
3. At each handoff, name the contract and what information crosses it.
4. Show one significant failure path and which component handles it.
5. Connect numbered steps to short code excerpts and verified source links.

Where relevant, distinguish logical ownership, process/network boundaries, and trust boundaries. Identify validation and authorisation at the point they actually occur. Do not add network, authentication, or persistence boxes to a package that has none.

## Explain the reason for modularity

Describe the reason for each consequential separation: independently changeable policy, reusable contract, isolated external dependency, deployment, or security responsibility. Show what a developer gains and which trade-off they accept.

Include one realistic change example: “To change this behaviour, edit this module and contract; the neighbouring module stays behind this interface.” Link to the relevant tests or checking command. This is more useful than calling the architecture “clean”, “decoupled”, or “modular”.

## Evidence and freshness

Each architecture page identifies the repository revision or release it describes. Links to code excerpts use that revision. A relevant accepted decision explains why; implementation and checks establish what currently exists.

Keep diagrams and code maps in the same repository as the code. A change to ownership, an exported contract, allowed dependency direction, or the documented flow triggers a review of the corresponding page. Preserve historic decisions; update the present-day explanation.

## The app, planned now and published later

The app remains outside this site's current publication scope. Plan these pages for after it moves into `unset-sh`:

| Page | Learning outcome |
| --- | --- |
| System overview | Place the app, AT Protocol, and external systems in context |
| Module boundaries | Understand responsibilities and allowed dependencies |
| A request through the system | Follow an actual operation across interfaces and contracts |
| Identity and trust boundaries | Understand where identity, authentication, authorisation, and validation happen |
| Data ownership and persistence | Know which module owns data and how storage is reached |
| Changing a feature | Locate the right module, preserve boundaries, and verify the change |

Use the future source repository's own instructions to locate its UI, entry points, product rules, external
adapters, shared code, and composition. This is an investigation checklist, not a prescribed folder layout or
a verified model of the future rewrite.

Before writing or publishing those pages, read the accepted architecture decisions, current code, and boundary checks at the app's then-current revision. Reconcile differences with the rewrite. Do not copy the old app documentation wholesale, expose placeholder app pages in navigation, or invent a future repository name.
