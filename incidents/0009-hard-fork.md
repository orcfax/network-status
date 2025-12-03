---
name: "Orcfax Incident Report"
title: "INCIDENT 0009 - Hard Fork"
published: 2025-12-03
status: "In Progress"
trigger: "Anomalous system behaviors"
---

## Initial Publish Date

2025-12-03

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

Cardano experienced a fork on November 21, 2025. On December 03, 2025 the Orcfax
price monitor component was reenabled resulting in a series of price deviations
which triggered an internal review. The review identified anomalous system
behavior linked to the mainnet fork.

## Assessment

Internal review found three nodes with Kupo databases which did not restart on
Cardano mainnet recovery from the fork; block height stalled at `172145747` and
resulted in the publication of stale data alongside live data. When price
monitoring was reenabled, this behavior was exaggerated and was flagged
internally.

All other nodes continued to operate as expected.

Upon discovery, publication was immediately stopped at
`2025-12-03T17:35:53.634854+00:00` and datapoints garbage collected. All nodes
were upgraded and the three affected nodes had their databases reindexed.

Publication resumed at `2025-12-03T19:55:44.374620+00:00` once all nodes came
back online and reported correctly.

## Additional Notes

The three affected nodes were hosted in India, Singapore, and Australia. All
three were operating node version `10.1.4` and it is suspected that other nodes
within the geographical area were also affected.

## Technical improvements

Resolutions

1. All nodes upgraded to version `10.5.3`
1. Ogmios upgraded to version `6.14.0`
1. Kupo upgraded to version `2.11.0`

We are investigating:

1. Connecting the validator to ogmios so that block height may be incorporated
   as a validation metric analogous to how time is used by the validator.
1. Completing a cnt-indexer refactor.
1. Strategies for better determining node health, e.g. using a block height
   comparison with its own database status to determined an unhealthy node.
1. Improving long-term monitoring of price data.

## Documentation improvements

1. Update recovery documentation with this new information to ensure a more
   complete checklist.
