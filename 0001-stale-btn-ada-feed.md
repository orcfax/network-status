---
name: Orcfax Incident Report
title: 'INCIDENT 0001 | Stale CNT prices (BTN-ADA)'
date: 2025-01-30
trigger: "anomalous system behaviors"
status: Resolved
---

## Trigger

* ⬛ suspected malware infections
* ⬛ access violations
* ✔️ anomalous system behaviors
* ⬛ human errors
* ⬛ unauthorized access attempts

## Date

2025-01-30

## Summary

Changes to liquidity pool addresses meant that BTN-ADA prices were stale from
January 30 to February 4.

## Status

Resolved

## Assessment

Address changes mean that CNT collectors are looking at incorrect data. Once
the issue was identified, CNT configuration was regenerated and collection
resumed as normal.

## Additional Notes

The BTN-ADA feed is not considered a production feed. It is a showcase feed
and currently unfunded. That being said, for consumers, stale data is a big
problem. An Oracle needs to be able to produce live data, or ensure that data
isn't published when it is erroneous. In this instance it would have been better
for the BTN-ADA feed to have stopped publishing entirely instead of publishing
stale information.

For the community requiring support of Oracle services it is important we
investigate the social aspects of maintaining a liquidity pool and
communicating changes. In a production scenario, for example, the change to the
liquidity pool may have been better communicated. In another scenario there
may be better technological triggers that we, as an oracle, can pick up on.
Both examples here could be topics of future Catalyst proposals.

## Technical improvements

We are investigating:

1. Regenerating CNT feed configuration on a more regular basis so as to identify
changes quicker.
1. Socio-technical approaches to following liquidity pools more effectively.
1. Identifying properties of stale feeds that can be implemented statelessly
in an oracle solution.

## Documentation improvements

1. N/A.
