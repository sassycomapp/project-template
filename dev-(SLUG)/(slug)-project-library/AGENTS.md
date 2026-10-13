# AGENTS.md — {slug} project library

This file adds the rules for this business's project library. It sits under the global `AGENTS.md`, which applies in full.

## What this library is

The project library of {project-name} (`{slug}`). It holds every document, decision and PDLF record for the business's apps. It holds no application code.

The business has five apps (`spec-five-app-architecture-model.md` in `project-library-global`):

- `{slug}-app1`, App 1, the development workspace. All feature work happens here.
- `{slug}-app2`, App 2, `master_template`, a clone of App 1's approved code.
- `{slug}-app3`, App 3, `blank_client_template`.
- `{slug}-app5`, App 5, the management app.
- App 4, each client's own instance, on the client's own Anvil account.

## Rules

1. **Never write `anvil.yaml`.** Anvil manages it. `opencode.json` enforces this.
2. **Code and documents are never mixed.** Documents go here. Code goes in the app folders, and only during building, with David's permission each time.
3. **No application is ever multi-tenant.** One app and one database per client, always.
4. **Never add forms or server modules to a client instance.** A change for one client is made in App 1 and released through App 2.
5. **The agent never commits or pushes.** Only David commits, with `commit-all`. Every PDLF step ends by asking David to run `/mb-close-out`.
6. **Search, read, apply.** Search GBrain first, then read the actual file each result points to before applying it.
7. **Plan reads, Build writes.** Plan mode never writes. Build mode writes only with David's approval.

## Where things go

| What | Where |
|---|---|
| The domain glossary | `docs-local/CONTEXT.md` |
| This application's decisions | `adr-local/` |
| Feature tickets | `pdlf-tickets/` |
| Everything a PDLF step produces | `pdlf-outputs/{step}/`, named `{slug}-{step}-{run}-{name}.md`, where `{run}` is `app` or the feature's short name |
| This application's own documents | `docs-local/` |

## Agent skills

### Issue tracker

Tickets are local markdown files in `pdlf-tickets/`. See `docs/agents/issue-tracker.md`.

### Triage labels

The five standard labels: `needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`. See `docs/agents/triage-labels.md`.

### Domain docs

Single context: the glossary is `docs-local/CONTEXT.md` and the decisions are in `adr-local/`. See `docs/agents/domain.md`.
