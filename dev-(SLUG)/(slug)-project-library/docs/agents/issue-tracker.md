# Issue tracker: local markdown

Tickets for this business live as markdown files in `pdlf-tickets/`, in this project library. The library is private; the app repositories are public, so tickets, which describe internal plans, never go there.

## Conventions

- **Create a ticket:** create `pdlf-tickets/<feature>/<ticket-slug>.md`, where `<feature>` is `app` for the whole application or the feature's short name. Use the frontmatter below.
- **Read a ticket:** read the file.
- **List tickets:** list the markdown files in `pdlf-tickets/` and filter by their frontmatter.
- **Comment:** append to the file under `## Comments`, with the date.
- **Labels:** edit the `labels` field. The labels are in `docs/agents/triage-labels.md`.
- **Close:** set `status: closed`.

## File template

```yaml
---
title: "Ticket title"
status: open          # open | closed
labels: []
created: YYYY-MM-DD
---

## Description

## Comments
```

## When a skill says "publish to the issue tracker"

Create a file in `pdlf-tickets/`.

## When a skill says "fetch the relevant ticket"

Read the file from `pdlf-tickets/`.
