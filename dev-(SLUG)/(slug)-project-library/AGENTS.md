---
document: AGENTS.md — project-library [{slug}]
doc-id: {slug}-0001
state: Live
date-created: YYYY-MM-DDTHHMMSS+0200
---

# AGENTS.md — project-library [{slug}]

> Inherits Global `AGENTS.md` in full. This file adds project-specific rules only.

## Project purpose

Planning, documentation, design, and GStack workflow workspace for the {project-name} application ({slug}). Not the live code repository. Live code lives in `{slug}`.

---

## Definitions

- **project-library** — this repo (planning/documentation/design). **{slug}** — the separate live application code repo.
- Other definitions as per Global `AGENTS.md`.

---

## Precedence order (highest to lowest)

1. Explicit user instruction in the current session
2. Global `AGENTS.md` rules
3. Hard Rules in this file
4. ADRs (`adr/`)
5. Specifications (`docs/`)
6. A skill's own default behavior

---

## Hard rules

### 1. anvil.yaml protection (enforced by opencode.json)
Never write to `anvil.yaml`. Anvil.yaml is always READ ONLY.

### 2. Two-repo separation
- `project-library/` = planning, docs, ADRs, wireframes. Does NOT go to Anvil.
- `{slug}/` = live Anvil code + `anvil.yaml`. Goes to Anvil via GitHub VC.
- Write to code repo only during coding phase, only for code files, never `anvil.yaml`.

### 3. GBrain cross-contamination discipline
Tag every GBrain result with its source project. Cross-project decisions require explicit human confirmation. Scope queries with `--source {slug}`.

### 4. No time-based references
Use Phase > Stage > Task > Sub-task hierarchy. Not "2 weeks" or "3 days."

### 5. No hardcoded colors
Every color through CSS custom properties. See `docs-local/DESIGN_palette_section.md`.

### 6. Plan reads, Build writes (enforced by opencode.json)
Plan never writes. Build writes only with user approval.

### 7. Skill ownership
Ask which skill to use before starting any task.

### 8. No deviation from the given task
Execute as specified. Propose deviations before acting.

### 9. Binding documents
ADRs, specs, rule files are binding. Check before starting. Flag conflicts.

### 10. Mandatory project context reading
Read `README.md` before every task.

---

## Workspace structure

| Folder | Purpose |
|---|---|
| `adr/` | Architecture Decision Records |
| `docs/` | Durable documentation, specs, UI standards |
| `wireframes/` | HTML wireframes and mockups |
| `screens/` | Screen HTML mockups and compliance checklists |
| `wip/` | Active work-in-progress |
| `output-gstack/` | GStack-produced reports |
| `output-opencode/` | OpenCode-produced reports |
| `output-matt-skills/` | Matt Pocock skill outputs |
| `workspace/gbrain/` | GBrain working files |
| `workspace/gstack/` | GStack working files |

---

## Artifact governance

Every artifact gets saved. Build actions only. Confirm save location in response.

| Producer | Destination |
|---|---|
| GStack | `output-gstack/` |
| OpenCode | `output-opencode/` |
| Matt Pocock skills | `output-matt-skills/` |

File type overrides: docs → `docs/`, ADRs → `adr/`, wireframes → `wireframes/`, screens → `screens/`.

Promotion: long-lived specs from `output-gstack/` → `docs/`. ADRs belong in `adr/`.

---

## GStack binary path override

Use `/mnt/c/mybizz/gstack/bin/<binary-name>` directly.

---

## Matt Pocock skills artifact governance

- `domain-modeling`, `grill-with-docs` → `CONTEXT.md` + `adr/`.
- `to-prd`, `to-issues`, `triage` → `.scratch/`.
- `setup-matt-pocock-skills` → `docs/agents/` + `CLAUDE.md`.
- `handoff`, `improve-codebase-architecture` → `%TEMP%` + `output-matt-skills/`.
- `teach` → `C:\mybizz\matt-skills-teach`.
- Others → ask the user.

---

## Source of truth

- `project-library/adr/` — architectural decisions
- `project-library/docs/` — documentation and specs
- `project-library/wireframes/` — visual references
- `{slug}/` — live code (read-only context)

Fact rule: do not use training data for project-specific facts. Validate GBrain research before use.

---

## Access model

- Plan: may read both repos. Never writes.
- Build: writes in `project-library` with user approval. Writes in `{slug}` only during coding phase with case-by-case permission.

---

## Task completion reporting

- Reports saved as `.md` in producer's output folder.
- `devlog-index.md` — reverse-chronological index of all reports.
- `judgement-trail.md` — flagged issues and developer decisions per task.
- If `devlog-index.md` or `judgement-trail.md` doesn't exist, create with header only (one-time scaffold exception).

---

## Timestamp Standard

Every date or timestamp this agent generates for a build artefact — front matter, register entries, alignment logs, learnings entries, backup folder names, devlog entries, or any other system-internal record — must follow the format and conversion method defined in:

`C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md`

This ADR specifies one mandatory method for generating the timestamp, with no fallback and no alternative. Read that document before generating any such timestamp. If anything about the required method is unclear, stop and ask the developer — do not improvise or substitute a different method.

This does not apply to client-facing data (bookings, invoices, activity logs, etc.), which follows the IANA-timezone-based rule in the same ADR's main Decision section, not this build-artefact standard.
