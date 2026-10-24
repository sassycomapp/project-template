# project-template

The model of a Mybizz business folder. PDLF's Step 11 copies `dev-(SLUG)/` to `C:\dev\dev-{slug}\` when a new business starts, and every existing business is brought into line with it.

## How Step 11 uses it

- Every `(SLUG)` and `(slug)` in a folder or file name, and every `{slug}` and `{project-name}` in a file, is replaced with the business's slug and name.
- Any `doc-id` line is removed from every copied document, so that the commit hook gives each new project's documents their own permanent identity.
- Each app folder holds the scaffold of its code repository: its `.gitignore`, its `README.md` and, for App 1 and App 5, its `tests\`, `scripts\` and `theme\assets\docs\` folders. The app's own code is brought in from GitHub after David creates the app in Anvil, with `git init`, `git remote add origin`, `git fetch` and `git checkout`, because a plain `git clone` needs an empty folder.
- The blank pre-project files are not kept here. They ship with PDLF, in `C:\pdlf\pdlf-library\templates-local\pre-project\`, and Step 11 places them in `pre-project\`.
- Every folder holds a `README.md` that says what belongs in it. A placeholder document is a stub that holds only its title, its purpose and its section headings.
- A file that a skill or a PDLF step creates is never stubbed, because the skill would take a stub for an existing file. The folder's `README.md` names it instead.

## Why it stays outside the documentation system

This repository is not a GBrain source and is not covered by the commit hook or `commit-all.sh`. The hook gives every document a permanent `doc-id`; because every new project is a copy of this template, every project would otherwise start with the same identities. David commits changes here by hand, with plain `git`.
