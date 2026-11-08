# {project-name} ({slug})

The folder of one Mybizz business. It holds the business's apps and its one project library.

| Folder | What it is |
|---|---|
| `{slug}-app1` | App 1, the development workspace: all feature work happens here. An Anvil app, public repository. |
| `{slug}-app2` | App 2, `master_template`: a clone of App 1's approved code, the dependency every client instance runs on. Public repository. |
| `{slug}-app3` | App 3, `blank_client_template`, the client app: App 1's table definitions, one startup module, the scheduled tasks and its dependency on App 2. Public repository. |
| `{slug}-app4` | The release image definition every client instance runs. A GitHub repository only, never an Anvil app. Public repository. |
| `{slug}-app5` | App 5, the management app. Public repository. |
| `{slug}-project-library` | The project library: every document, decision and PDLF record for the whole business. Public repository. |
| `wip` | David's personal working folder. Not part of the project and not a repository. |
| `{slug}-project-context` | Present only during Step 11, for a business that brought its own material into PDLF: its existing project library, moved here whole, read-only, until Step 11 moves its documents into the project library and retires it. Never opened in OpenCode. |

App 4, each client's own instance, runs on DigitalOcean, in its own container with its own database, and has no folder here. Code and documentation are never mixed. No application is ever multi-tenant.

Every repository is public, so no secret, key or client data is ever committed to any of them. Keys live only in each app's `.env`, which is never committed.
