---
name: "Orcfax Incident Report"
about: "Orcfax standard template for issue reporting"
title: "INCIDENT 0005 - protocol upgrade issues"
published: 2025-06-27
status: "Resolved"
trigger: "Human errors"
---

## Initial Publish Date

2025-06-27

## Status

-   [ ] Under Review
-   [ ] Identified
-   [ ] In Progress
-   [ ] Mitigated
-   [x] Resolved

## Trigger

-   [ ] Suspected malware infections
-   [ ] Access violations
-   [ ] Anomalous system behaviors
-   [x] Human errors
-   [ ] Unauthorized access attempts

## Summary

Upgrading the Orcfax network's pairs and publication mechanisms created various
gaps in publication across a number of hours.

## Assessment

Gaps in publishing were caused by various factors during the protocol upgrade,
but primarily the new publication mechanism "pubwatch" and package updates on
various servers connected with publication. Publication timing has been resolved
and server components requiring specific versions are now pinned or soon to be
pinned.

## Additional Notes

This is the first time since the launce of mainnet v1 in September 2024 that
Orcfax has attempted to cycle feeds, as well as upgrade components that had
previously been tested on preview for the last few months.

pubwatch, a mechanim for monitoring gaps in publication was configured
incorrectly, resulting in gaps in publication larger than the configured
interval. pubwatch checks were configured too sparinggly, creating a bigger
window of error than required by integrators. A publication that might be
required in the next 16 minutes might be missed by one check resulting in a
gap longer than an hour before the next check. Additional checks have now been
added.

On various servers, packages were upgraded causing a conflict between expected
versions of software and those that were running. In the case of the
transaction building component the Javascript runner, Deno was in conflict
with the publication scripts. The problem is understood now and the softwaare
can no longer be upgraded unless the team explicitly set out to do so.

## Technical improvements

We are investigating:

1. Continuing to improve alignment of production with test servers to reduce
skew in understanding.
1. Practicing upgrade protocols more often to more completely understand the
processes invovled.

## Documentation improvements

1. Improving devops documentation so that the team remains fully-prepared for
any issues caused as a result of upgrading the protocol in future.
