# project-template

The model of a Mybizz business folder. PDLF's Step 11 copies `dev-(SLUG)/` to `C:\dev\dev-{slug}\` when a new business starts, and every existing business is brought into line with it.

## How Step 11 uses it

- Every `(SLUG)` and `(slug)` in a folder or file name, and every `{slug}` and `{project-name}` in a file, is replaced with the business's slug and name.
- Any `doc-id` line is removed from every copied document, so that the commit hook gives each new project's documents their own permanent identity.
- The app folders `(slug)-app1`, `-app2`, `-app3` and `-app5` are empty placeholders. Each is filled by cloning that app's repository from GitHub after David creates the app in Anvil.
- The blank pre-project files are not kept here. They ship with PDLF, in `C:\pdlf\pdlf-library\templates-local\pre-project\`, and Step 11 places them in `pre-project\`.

## Why it stays outside the documentation system

This repository is not a GBrain source and is not covered by the commit hook or `commit-all.sh`. The hook gives every document a permanent `doc-id`; because every new project is a copy of this template, every project would otherwise start with the same identities. David commits changes here by hand, with plain `git`.
