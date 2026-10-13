# Domain docs

How the engineering skills read this business's domain documents.

## Layout

Single context. The business has one vocabulary and one set of decisions, shared by all its apps.

- **The glossary:** `docs-local/CONTEXT.md`.
- **The decisions:** `adr-local/`. Global decisions are in `project-library-global` and are referenced, never copied.
- **The code:** in the app folders beside this library, `{slug}-app1`, `{slug}-app2`, `{slug}-app3` and `{slug}-app5`. Read code there directly.

## Before exploring, read these

- `docs-local/CONTEXT.md`
- the decisions in `adr-local/` that concern the task

If either does not exist yet, carry on without it. Step 16 creates the glossary and the decisions as terms and decisions are settled.

## Use the glossary's words

When anything you write names a domain concept (a ticket title, a proposal, a test name), use the term exactly as `CONTEXT.md` defines it, never a synonym.
