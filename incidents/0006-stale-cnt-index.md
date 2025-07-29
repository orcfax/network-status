---
name: "Orcfax Incident Report"
about: "Orcfax standard template for issue reporting"
title: "INCIDENT 0006 - stale CNT index value"
published: 2025-07-29
status: "In Progress"
trigger: "Anomalous system behaviors"
---

## Initial Publish Date

2025-07-29

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

Orcfax's CNT price indexer registered stale prices in MinSwapV2 liquidity
pools for a number of hours on May 24 for INDY-ADA, and July 15 for ADA-DJED.
The price was due to a sharp change caused by a big liquidity movement within
the respective pools. We are in the progress of fixing overly cautious
guard rails in the CNT indexing software and monitoring liquidity pool
activities manually to understand all such situations better.

## Assessment

Large movements of liquidity in MinSwapV2 pools for INDY-ADA and ADA-DJED
caused stale values to be returned to CNT collector nodes resulting in large
price differentials versus reality in the respective CNTs.

UTxOs associated with the INDA-ADA and ADA-DJED were not updated correctly
and so information used to calculate prices was incomplete.

The CNT indexer needs to be able to work more dynamically when large sums
of liquidity are moved in respective dexes. Such movements have been
monitored manually by the Orcfax team since the first recorded incident
and updates made to the CNT indexer as a result. The updates are currently
in testing on developer machines and will soon be on preview.

## Additional Notes

It was recognized that issues reading incorrect values from
liquidty pools could be mitigated by manually triggering updates two to
three times a day and as a result, even with new fixes, the indexer will be
restarted at uneven intervals during the day to prevent this issue or other
possible liquidity manipulations on-chain.

## Technical improvements

We are investigating:

1. Updating indexer software to correctly register liquidity pool changes
and update UTxOs used for price calculation accordingly.
1. Irregularly restarting indexers multiple times throughout the day to
mitigate issues associated with fluctuation of liquidity pool.

## Documentation improvements

N/A.
