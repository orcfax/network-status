---
name: "Orcfax Incident Report"
title: "INCIDENT 0002 - Validator stall"
published: 2025-02-26
status: "Under Review"
trigger: "Anomalous system behaviors"
---

## Initial Publish Date

2025-02-26

## Status

-   [x] Under Review
-   [ ] Identified
-   [ ] In Progress
-   [ ] Mitigated
-   [ ] Resolved

## Trigger

-   [ ] Suspected malware infections
-   [ ] Access violations
-   [x] Anomalous system behaviors
-   [ ] Human errors
-   [ ] Unauthorized access attempts

## Summary

Mainnet publication stalled from 20:35 UTC to 07:33 UTC between 24th and 25th 
February.

## Assessment

The Orcfax validator suffered a deadlock trying to retreive a current price 
after consensus failed.

## Additional Notes

Internal reporting identified the publishing issue and it should have been 
investigated shortly after the alert was raised, however, it remain unnoticed.

We suspect a deadlock is being caused by incompatibilities in the underlying 
Python packages.

The network should be able to recover from an incident like this.

While we haven't any integrators subscribed to the Orcfax service, impact 
remains minimal. In cases where this would have happened in a production 
environment we would anticipate more eyes on the issue. We also recommend using 
Orcfax in concert with a backup oracle via another oracle service, or 
temporarily local backup.

## Technical improvements

* We anticipate load-balancing can help to imporve resillience.
* The Python issues have been under investigation and will continue to be 
looked at.
* Alerting will be investigated to provide better delineation between warnings 
and errors.

## Documentation improvements

There are no documentation improvements being investigated for this issue.
