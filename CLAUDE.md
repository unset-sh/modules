# CLAUDE.md: unset-sh/modules

## Where this repository fits

This is `unset-sh/modules`: marketplace modules for unset.sh, meaning the module contract, the reviewed modules
and the list the marketplace reads. A module is a small app a member turns on or off.

- **Belongs here:** the module contract (manifest, permissions, the messages between a module and unset.sh), the
  starter module, the modules themselves with their own record types, the generated list of accepted modules and
  the block list, the checks every module must pass, and the developer guide.
- **Does not belong here:** loading a module, its screen and the marketplace screens (that is `unset-sh/web`);
  a member's on or off state and every write made for a module (that is `unset-sh/backend`); the `sh.unset.*`
  record types (that is `unset-sh/lexicons`); serving module files and their domain (that is
  `unset-sh/deployment`); colours, fonts and icons (that is `unset-sh/brand`).
- **Uses:** `unset-sh/tooling` through the branch-policy workflow at a full commit; `unset-sh/agent-kit` through
  the checked copy under `.claude/`. **Used by:** `unset-sh/web` and `unset-sh/backend`, planned, once a contract
  exists.
- **Licence:** follows the organisation rule today (AGPL-3.0-only, no outside code). The owner has not yet set
  the licence for the contract, the starter module and outside developers' modules; ask before any of it
  becomes permissive or any outside work is merged.

The map of every unset.sh repository is <https://github.com/unset-sh/.github/blob/main/MAP.md>. Read it before
moving work between repositories or starting work that might belong elsewhere.

**Keep the map current.** When a change here adds, removes or moves a responsibility, changes what this
repository uses or ships, or renames or archives it, open a pull request on `unset-sh/.github` that updates
`repos.json` (run `npm run map` there) and update this section to match.

## Rules

- This is a foundation. No contract, module, list or marketplace exists. Do not claim otherwise, and do not add
  empty folders or placeholder code. Folders appear with their first file.
- The owner set this direction (2026-11-23): all modules live in this one repository first; every module is
  reviewed and accepted by unset before members see it; a module is a sandboxed web app given a screen inside
  unset.sh, to be confirmed by a browser test. The README lists the working assumptions that are not decided.
  Building on one of them needs the owner's decision first, and the organisation decision record that carries it.
- A module's code is untrusted. It never runs in unset.sh's own pages or servers, never receives a session,
  token or cookie, and never writes under `sh.unset.*`. Do not weaken this to make a module work; stop and ask.
- This repository is public and will take pull requests from forks. Workflows run on GitHub-hosted runners
  only, triggered by `pull_request`, never `pull_request_target`, and no workflow a fork's pull request can
  reach holds a secret or a token that can write. A fork's pull request brings its own workflow file, so a
  condition in the file is not a fence.
- Do not merge a pull request from outside the organisation until the owner opens contributions.
- A change to what a module is allowed to do, or to the contract once it is published, is expensive to reverse:
  stop and ask.

## Commands

No package manifest exists yet; add one with the first code, with one `check` command that runs every check.

```sh
node .claude/agent-kit/sync.mjs --check
```
