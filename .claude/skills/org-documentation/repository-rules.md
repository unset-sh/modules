# Repository facts and adoption

The [standard](standard.md) is the shared instruction body. Each repository supplies only its local facts in
its existing instructions. Do not paste independent copies of the standard across repositories. The shared
engineering rules already point assistants to `org-documentation`.

## Ownership

The source repository owns page text, diagrams, examples, and their evidence. `unset-sh/docs` owns the renderer,
supported metadata and components, page composition, and navigation behaviour. The brand package owns shared
visual values and assets. Keep those responsibilities separate; source pages do not supply their own theme.

Take renderer-specific acceptance rules from the website's contribution documentation. The metadata in this
skill is still a proposal, not proof that the renderer accepts or checks it. Run the source repository's actual
checks and the shared preview checks available for the change; report any unavailable verification.

## Repository-owned facts

Each participating repository documents these facts in its existing `CLAUDE.md`, `AGENTS.md`, or linked contributing instructions, following its established loader pattern:

| Fact | Repository supplies |
| --- | --- |
| Public documentation source | Actual source directory; propose `docs/site/` for a new source only if it fits the repository |
| Export destination | Its exact `<repo>/` section in `unset-sh/docs` |
| Local verification | Actual commands for examples, generated reference, and content checks |
| Site preview | The supported central preview command and required versions, once implemented |
| Source truth | Schemas, public entry points, generators, tests, and relevant accepted decisions |
| Source provenance | Where checked revisions and exported source revisions are recorded |
| Review ownership | The repository's existing review process, not an invented team |
| Periodic verification | Responsible maintainer, review interval, and where results are recorded |
| Documentation impact check | Actual configured check and reviewed no-change reason process, if adopted |
| Licence | The source documentation and any separate asset licences |

Until these facts are supplied, do not guess paths, commands, owners, or a source revision. Adoption does not replace stricter security, protocol, or contribution rules.

## Adoption checklist for each source

- Take a reviewed `agent-kit` commit through the skill `org-kit-update`; do not modify its installed copy.
- Fill in the local facts above. Link human contributing guidance to the installed
  `.claude/skills/org-documentation/standard.md` and its templates, so readers and assistants use the same version.
- Pick one useful learning page and one architecture or conceptual page as the first examples of the standard.
- Add only the categories those pages need; link both reader routes to shared reference.
- Apply the standard's change-review and periodic-verification rules to the repository's code, workflows and ownership. Explain important workflows using their actual source files and checked revisions.
- Check the export and rendered result before enabling publication.

Shipping this skill does not enroll repositories, configure export jobs, or enable publication. Each source
takes the kit commit that contains it through its own reviewed update.

Workflow automation and executable checks belong in their implementing repositories, not this text-only kit.
Shared executable checks belong in `unset-sh/tooling` (org-0006); a reusable documentation-impact check
there remains proposed until it lands. Each repository must explicitly adopt and configure an available check before claiming it is
enforced. Keep any reviewed no-change reason with the source pull request; do not treat a passing check as a
substitute for reviewing meaning, examples, and current behaviour.
