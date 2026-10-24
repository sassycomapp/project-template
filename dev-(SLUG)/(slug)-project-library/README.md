# {project-name} — Project Library

The project library of {project-name} (`{slug}`): every document, decision and PDLF record for all of the business's apps. It is the business's GBrain source `{slug}-project-library`. It holds no application code; the code is in the app folders beside it.

## Folders

| Folder | What it holds |
|---|---|
| `pre-project/` | The three pre-project files David fills in for a new application: the brief, the scoping ideas, and the constraints and notes. |
| `docs-local/` | This application's own documents, including `GLOSSARY.md`, the domain glossary. |
| `docs-standard-local/` | Standard documents for this application, modelled on those in `project-library-global`. |
| `adr-local/` | Decisions that belong to this application only. Global decisions are referenced where they live. |
| `policy-local/` | Policies that belong to this application only. |
| `standard-operating-procedures-local/` | Procedures (`sop-` prefix) that belong to this application only. |
| `prompts-local/` | Prompts that belong to this application only. |
| `ui/` | Wireframes and screens, one folder per form, named after the Anvil forms. |
| `docs/agents/` | How the Matt Pocock skills work in this library: where tickets live, the triage labels, and where the glossary and decisions are. |
| `pdlf-tickets/` | The feature tickets, one markdown file each. |
| `pdlf-outputs/` | One folder per PDLF step (`a01` to `f46`). Everything a step produces for this business is kept in its folder: the Step Receipt and a copy of every output. |
| `.out-of-scope/` | Ideas the triage skill set aside as out of scope, kept so they are not raised again. |
| `V2/` | What has been deferred to version 2. |
| `wip/` | The project's working to-do list. |

## How this library is worked on

Agents follow `AGENTS.md`. PDLF runs from `C:\pdlf` and writes here only what belongs to this business. Only David commits, with `commit-all`.
