# modules

Marketplace modules for unset.sh: the module contract, the reviewed modules and the list the marketplace reads.

A module is a small app a member can turn on or off from the unset.sh marketplace. This repository is where
modules are built, reviewed and listed, and where developers outside unset will be able to add their own.

**Status: repository foundation only.** No contract, no module, no list and no marketplace exist yet. What
follows describes the direction, and the parts marked as working assumptions are not decided.

## Direction

Set by the owner:

- A member turns a module on or off. Turning one off stops it; it never deletes the member's own records.
- To begin with, every module lives in this one repository. Modules kept in other repositories may come later.
- Every module is reviewed and accepted by unset before members can see it.
- A module is a sandboxed web app. unset.sh gives it a screen inside its own view, and the module's code never
  runs as part of unset.sh's own pages or servers. This is to be confirmed by a browser test before any build.

Working assumptions, until the owner decides:

- A module never signs in. unset.sh acts for it, within the permissions the member approved when turning it on.
- A module's own record types live under a domain its developer controls, never under `sh.unset.*`.
- A visitor to a profile never runs module code. unset.sh draws what a module adds to a page.
- A module is listed when it reaches `main`, and only the owner promotes to `main`.

## What belongs here

| Belongs here | Goes elsewhere |
| --- | --- |
| The module contract: the manifest, the permissions a module may ask for, the messages between a module and unset.sh | Loading a module, showing its screen and the marketplace screens: [web](https://github.com/unset-sh/web) |
| The starter module a developer copies | Turning a module on or off for a member, and every write made for a module: [backend](https://github.com/unset-sh/backend) |
| The modules themselves, one folder each, with their own record types | The `sh.unset.*` record types: [lexicons](https://github.com/unset-sh/lexicons) |
| The generated list of accepted modules, and the list of blocked ones | Where module files are served from, and its domain: [deployment](https://github.com/unset-sh/deployment) |
| The checks every module must pass, and the guide for developers | Colours, fonts and icons: [brand](https://github.com/unset-sh/brand) |

Folders appear with their first file. None exists yet.

## Contributing

Outside contributions are not open yet. They open once the contract, the checks and the review steps exist and
the owner has set the licence for outside work. Until then a pull request from outside the organisation is not
merged. The organisation's [contributing notes](https://github.com/unset-sh/.github/blob/main/CONTRIBUTING.md)
apply, and a security problem is reported as its
[security policy](https://github.com/unset-sh/.github/blob/main/SECURITY.md) says, never in a public issue.

## Working here

Read [CLAUDE.md](CLAUDE.md), [AGENTS.md](AGENTS.md) and the
[organisation map](https://github.com/unset-sh/.github/blob/main/MAP.md) first. Work goes on your own branch
and lands through a pull request into `staging`. `main` is what is released, and only the owner promotes to it.

The one check today:

```sh
node .claude/agent-kit/sync.mjs --check
```

It confirms that the copy of [agent-kit](https://github.com/unset-sh/agent-kit) under `.claude/` matches its
lock. CI runs it on every pull request and on `staging` and `main`, on GitHub-hosted runners.

## Licence

Copyright (c) 2026 Alex (Undefined6799). Everything here is [AGPL-3.0-only](LICENSE) for now. The licence for
the contract, the starter module and outside developers' modules is the owner's to set before contributions
open. Work we use from others keeps its own licence.
