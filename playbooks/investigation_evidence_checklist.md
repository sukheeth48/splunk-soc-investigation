# SOC Investigation Evidence Checklist

## Case Details
- [ ] Record the alert or case ID.
- [ ] Record the detection name and time range.
- [ ] Record the affected username.
- [ ] Record the source IP address.

## Authentication Evidence
- [ ] Confirm the number of failed authentication events.
- [ ] Confirm the number of successful authentication events.
- [ ] Review event timestamps and sequence.
- [ ] Verify that events belong to the same username and source IP.
- [ ] Save the SPL search used to validate the alert.

## Contextual Investigation
- [ ] Review surrounding authentication activity.
- [ ] Check whether the login was expected using authorized records.
- [ ] Review additional endpoint or identity evidence when available.
- [ ] Document evidence that supports or contradicts the alert.

## Decision and Handover
- [ ] Record the investigation findings.
- [ ] Explain the reasoning behind the disposition.
- [ ] Document unresolved questions.
- [ ] Record the recommended next action.
- [ ] Escalate according to organizational procedures when necessary.

## Evidence Quality
- [ ] Separate observed facts from assumptions.
- [ ] Do not label an account compromised without sufficient evidence.
- [ ] Do not treat synthetic lab data as evidence of a real incident.
- [ ] Remove secrets and sensitive information from portfolio screenshots.

## Lab Status
This checklist is a reusable investigation aid. It has not been applied to a real production incident.
