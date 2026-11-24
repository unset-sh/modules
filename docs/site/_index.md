---
title: "Modules"
description: "Marketplace modules for unset.sh: the module contract, the reviewed modules and the marketplace list."
type: docs
cascade:
  type: docs
menus:
  main:
    weight: 140
params:
  doc_kind: overview
---

`unset-sh/modules` is where unset.sh marketplace modules are built, reviewed and listed. A module is a small app a
member can turn on or off from the marketplace.

**Status: repository foundation only.** No contract, module, list or marketplace exists yet. The direction below is
set; the working assumptions are not decided.

## Direction

- A member turns a module on or off.
- To begin with, every module lives in this one repository.
- Every module is reviewed and accepted by unset before members can see it.
- A module is a sandboxed web app with its own screen inside unset.sh. Its code never runs as part of unset.sh's
  own pages or servers. A browser test confirms this before anything is built.

## Working assumptions

- Turning a module off stops it and never deletes the member's own records.
- A module never signs in; unset.sh acts for it within the permissions the member approved.
- A module's own record types live under a domain its developer controls, never under `sh.unset.*`.
- A visitor to a profile never runs module code.

## Contributing

Outside contributions are not open yet. They open once the contract, the checks and the review steps exist and the
licence for outside work is set.

The [repository README](https://github.com/unset-sh/modules#readme) has the full notes. This section is exported
from `docs/site/` in `unset-sh/modules`; edit it there.
