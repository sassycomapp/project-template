---
title: "deployment-procedures"
---
# {project-name} — Deployment Procedures

How a release moves from App 1 through App 2 and the release image to the client instances, and how it is rolled back.

**Standard:** [[[default:specifications-global/spec-deployment]]](C:/dev/project-library-global/specifications-global/spec-deployment.md)

## Deployment Model

Every release is staged: App 5's Release action verifies the release image's signature, then moves the test client instance to it by its digest, then 10% of client instances, then every client instance. Each stage passes its health check before the next starts; a failed health check rolls that stage back automatically, stops the release and messages Mybizz ([[[default:adr-global/adr-dependency-update-model|Dependency Update Model]]](C:/dev/project-library-global/adr-global/adr-dependency-update-model.md)).

## Schema Migration

## Post-Deploy Verification

## Rollback

## Rollback Triggers

## Deployment Checklist

- [ ] No High or Critical image finding older than 14 days, and no end-of-life software in the image
- [ ] The release image is signed

## Account-Level Failures

| Scenario | Recovery | Prevention |
|---|---|---|
| DigitalOcean region outage or account suspension | App 5's **Rebuild** action ([[[default:specifications-global/spec-deployment\|Deployment Specification]]](C:/dev/project-library-global/specifications-global/spec-deployment.md) section 10) | Locked R2 backup copies; the rebuild tested before the first paying client; a second payment card and billing alerts on the account |
| Mybizz's SES sending suspended | Outgoing email queued in each instance's retry queue and sent when sending returns | Each client's SES tenant reputation policy; monthly email caps per client; two CloudWatch alarms below Amazon's review levels |
| Any account compromised | Follow `incident-response-plan.md` | A hardware security key on every supplier account; two scoped DigitalOcean keys; the cluster's trusted sources; locked backup copies |

