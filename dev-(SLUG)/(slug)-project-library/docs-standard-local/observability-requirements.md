---
title: "observability-requirements"
---
# {project-name} — Observability Requirements

What the application logs, measures and alerts on, and how long logs are kept.

**Standard:** [[[default:specifications-global/spec-observability]]](C:/dev/project-library-global/specifications-global/spec-observability.md)

## Logging

## Metrics

## Alerts

App 5 runs the platform checks of [[[default:specifications-global/spec-observability|Observability Requirements]]](C:/dev/project-library-global/specifications-global/spec-observability.md) section 4 for every client instance of the business, and messages Mybizz:

- **Critical — act now:** no heartbeat from an active instance for 30 minutes (App 5's status endpoint reports a fault, which DigitalOcean Uptime emails to Mybizz); a client's SES tenant paused by its reputation policy; either CloudWatch alarm on Mybizz's SES account; a client at any hard limit of [[adr-fair-use-limits]]; a 2 GiB container above 80% of its memory; a nightly copy missing or a monthly restore drill failed; a client domain not resolving or its certificate invalid.
- **Warning — watch:** a container or the cluster resized ([[adr-automatic-resizing]]); a client at any warning level of [[adr-fair-use-limits]]; a client domain's registration expiring within 30 days.

## Heartbeat to App 5

- Sent every 15 minutes, with the instance's Bearer token ([[[default:adr-global/adr-mybizz-management-visibility|Mybizz Management Visibility]]](C:/dev/project-library-global/adr-global/adr-mybizz-management-visibility.md)).
- Carries the client database's size and the client's AI and voice spend for the month, with the instance's status and release version.
- No customer personal data is sent to App 5.

## Log Retention

