---
name: "Orcfax Incident Report"
title: "INCIDENT 0003 - Arkly server full"
published: 2025-04-08
status: "Resolved"
trigger: "Anomalous system behaviors"
---

## Initial Publish Date

2025-04-08

## Status

-   [ ] Under Review
-   [ ] Identified
-   [ ] In Progress
-   [ ] Mitigated
-   [x] Resolved

## Trigger

-   [ ] Suspected malware infections
-   [ ] Access violations
-   [x] Anomalous system behaviors
-   [ ] Human errors
-   [ ] Unauthorized access attempts

## Summary

Arweave publications stalled from 11:00 April 5, to 23:00 April 7.

## Assessment

The Arweave server's uptime of 299 days led to a huge build-up of Arkly/Arweave
packages. The number of packages was greater than that allowed by the code's
write functions and so uploads were not possible. The packages directory was
cleared and uploads were possible once again.

## Additional Notes

For consumers the complete audit trail of anything published between the two
dates is not available. Given no consumers are reliant on Orcfax's feeds at
present the impact is minimized.

Orcfax's audit trail is required when there is an on-chain price-dispute. This
is an unlikely scenario and so the risk is further minimized, however, Orcfax
remains committed to making sure that this important para-, and meta-data is
available at all times.

## Technical improvements

We are investigating:

1. Using systemd-tmpdir more effectively for management of transitory files on
the Arkly platform.
1. Monitoring Arkly storage if a better tmpdir solution cannot be determined.

## Documentation improvements

N/A.
