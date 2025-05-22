---
name: "Orcfax Incident Report"
about: "Orcfax standard template for issue reporting"
title: "INCIDENT 0004 - Validator stall"
published: 2025-05-22
status: "In Progress"
trigger: "Anomalous system behaviors"
---

## Initial Publish Date

2025-05-22

## Status

-   [ ] Under Review
-   [ ] Identified
-   [x] In Progress
-   [ ] Mitigated
-   [ ] Resolved

## Trigger

-   [ ] Suspected malware infections
-   [ ] Access violations
-   [x] Anomalous system behaviors
-   [ ] Human errors
-   [ ] Unauthorized access attempts

## Summary

The Orcfax validator stalled on 16 May 2025 from 00:00 UTC until 06:30 UTC.
No price updates were published during this time.

## Assessment

The issue is caused by an issue with Python's `multiprocessing.pool()` causing
a deadlock intermittently when processing data. The issue is known and under
investigation.

## Additional Notes

The issue appears to be in the Python standard library and so finding an
immediate solution has not been straightforward. We are looking at modifying
FastAPI parameters as well as alternatives to `multiprocessing.pool()` at the
center of the validation code. Until the issue is resolved the Orcfax team
have accepted the risk and anticipate using greater devops coverage to
correct publication when an issue happens.

At the time of the incident the team were unavailable to restart the
validation process and so the incident went unresolved longer than antiicpated.

## Technical improvements

We are investigating:

1. Correcting the issue in the validator with other standard library
components.
1. Creating a more reliable fallback mechanism when the primary validator
becomes unresponsive.

## Documentation improvements

1. Improved devops documentation so that more staff can engage with the
issue if it happens again.
