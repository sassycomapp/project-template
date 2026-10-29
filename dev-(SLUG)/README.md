# {project-name} ({slug})

The folder of one Mybizz business. It holds the business's apps and its one project library.

| Folder | What it is |
|---|---|
| `{slug}-app1` | App 1, the development workspace: all feature work happens here. An Anvil app, public repository. |
| `{slug}-app2` | App 2, `master_template`: a clone of App 1's approved code, the dependency every client instance runs on. Public repository. |
| `{slug}-app3` | App 3, `blank_client_template`: App 1's data table schema, one startup module and its dependency on App 2. Public repository. |
| `{slug}-app5` | App 5, the management app. Public repository. |
| `{slug}-project-library` | The project library: every document, decision and PDLF record for the whole business. Public repository. |
| `wip` | David's personal working folder. Not part of the project and not a repository. |
| `{slug}-project-context` | Present only for a business that brought its own material into PDLF: its existing project library, moved here whole by Step 11, read-only. Public repository. Never opened in OpenCode. |

App 4, each client's own instance, lives on the client's own Anvil account and has no folder here. Code and documentation are never mixed. No application is ever multi-tenant.

Every repository is public, so no secret, key or client data is ever committed to any of them. Keys live only in each app's `.env`, which is never committed.
