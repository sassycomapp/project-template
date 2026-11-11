---
title: "integration-architecture"
---
# {project-name} — Integration Architecture

Every outside service the application uses, and how it is connected.

**Standard:** [[[default:specifications-global/spec-integration]]](C:/dev/project-library-global/specifications-global/spec-integration.md)

## Payment Gateways

## Email

- Every email of a client instance goes through Amazon SES in Mybizz's AWS account, with one SES tenant per client.
- **Limits:** each client's SES tenant carries SES's standard reputation policy, which pauses that client's sending alone. Marketing email is capped at 25,000 a month and all email at 50,000 a month per client, with warnings at 20,000 and 40,000 ([[adr-fair-use-limits]]; [[[default:specifications-global/spec-integration|Integration Specification]]](C:/dev/project-library-global/specifications-global/spec-integration.md) section 2.6).
- **Received email files** are deleted from S3 once processed; an S3 lifecycle rule deletes any left after 7 days.

## CRM

## Client Storage (R2)

## Webhooks

## Background Tasks

## Timezones

## Domain and Provisioning

- The website record of each client domain is proxied through Cloudflare, with the web application firewall, DDoS protection and bot blocking switched on in the client's Cloudflare account. The email records stay unproxied.

## Offboarding

