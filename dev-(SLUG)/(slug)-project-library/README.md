---
document: README — project-library [{slug}]
doc-id: {slug}-0002
state: Live
date-created: YYYY-MM-DDTHHMMSS+0200
---

# {Project Name} — Project Library

Planning, documentation, and specification repository for the {project-name} project.

## Structure

| Folder | Purpose |
|---|---|
| `pre-project/` | Developer's first-thoughts, scoping ideas, ideation notes |
| `pdlf/` | PDLF orchestrator artifacts: devlog, ISA, BFT checkpoints |
| `adr/` | Architecture Decision Records |
| `docs/` | Durable application documentation and specifications |
| `wireframes/` | HTML wireframes, mockups, visual layout references |
| `screens/` | Screen HTML mockups and compliance checklists |
| `wip/` | Active work-in-progress |

## PDLF

This project is managed using PDLF — a contiguous, stage-gated, memory-compounding
development strategy. Type `/pdlf` in OpenCode to init or resume.

**Code repo:** `../{slug}/` (Anvil-connected, GitHub VC)
