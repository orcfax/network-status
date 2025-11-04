## Initial Publish Date

2025-11-04

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

A global AWS outage on 16 October 2025 affected arweave.net and therefore
the ability for Orcfax to archive its fact-statements. Archiving was
temporarily paused to allow on-chain publishing to continue. The
arkly service will implement a fall-back mechanism to remove arweave.net as
a single point of failure.

## Assessment

It was noticed that Orcfax publishing was delayed due to an issue
connecting to arweave.net via arkly.io. After a brief investigation, it was
clear that the arweave.net gateway was reliant on AWS and was not
abstracting a load-balancing or fallback mechanism underneath. Due to the
global AWS outage on October 16, it was not possible to contact the service.

A decision was made to pause archiving, allowing on-chain publishing to
continue and services to keep using Orcfax data.

Archives were enabled as soon as the AWS outage was resolved.

## Additional Notes

Arweave is used by Orcfax as a decentralized L0. It must be possible to
communicate with Arweave at all times, and a centralized outage such as the
one experienced by AWS must not be able to affect that. The outage served as
an important reminder that we cannot take for granted what "decentralized"
may or may not mean when it comes to certain services.

During the outage, evidence was gathered that allowed us to identify
four or five other Arweave gateways that could be used by Orcfax to fall
back on if one gateway becomes unreachable due to AWS.

Orcfax will enable the use of more than one Arweave gateway in the
arkly.io service, which should reduce the impact of such outages in the
future.

## Technical improvements

We are investigating:

1. Upgrading arkly.io to implement additional fallback arweave gateways.

## Documentation improvements

There are no documentation improvements planned at this time.
