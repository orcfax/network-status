---
name: "Orcfax Incident Report"
about: "Orcfax standard template for issue reporting"
title: "INCIDENT 0007 - validator stall"
published: 2025-08-17
status: "Mitigated"
trigger: "Anomalous system behaviors"
---

## Initial Publish Date

2025-08-28

## Status

-   [ ] Under Review
-   [ ] Identified
-   [ ] In Progress
-   [x] Mitigated
-   [ ] Resolved

## Trigger

-   [ ] Suspected malware infections
-   [ ] Access violations
-   [x] Anomalous system behaviors
-   [ ] Human errors
-   [ ] Unauthorized access attempts

## Summary

Orcfax's primary validator stalled and was unable to be restarted for 11 hours
resulting a total network outage during that time. Updated validator code has
been reviewed and deployed and we anticipate stall issues should now be
mitigated.

## Assessment

As per the assessment in [Incident 0002][incident-2] Orcfax has been wrestling
with library incompatibiilities in the validator node. These caused a network
stall on August 17. While the stall was recognized early staff vacations meant
that no one was able to recover the network in time.

New code was released onto the validator node on August 27 and it replaces
the Python Requests library with AIOHTTP allowing us to remove multiprocessing
code with pure async. There should be a much greater compatibility between
the new Python libraries.

Staff communication procedures have been looked at a new protocols within
Discord will be adopted to attempt to mitigate down-time in future.

Orcfax will continue to investigate cross-server signalling that will better
enable intermediate recovery in such situations onto a fallover server.

The Orcfax team believes, however, after extensive time taken to research
this issue, and testing on our Preview network, that the new code should
positively affect such stalls in the future.

[incident-2]: 0002-validator-stall.md

## Additional Notes

N.A.

## Technical improvements

Alongside the latest validator deployment we are investigating:

1. Enabling a fall-back server for the validator when one stalls to
provide intermediate relief for such situations.
1. Continuing to investigate decentralization of the Orcfax network to
benefit from the beneficial redundancy that brings.

## Documentation improvements

1. Internal communication procedures and notices of availability.
