# Reusable Detection Query Validation

## Objective
Validate the reusable five-minute authentication detection query against the imported sample authentication dataset.

## Query
`queries/05_five_minute_auth_detection.spl`

## Observed Results
- Matching result rows: 1
- Failed attempts in the returned row: 3
- Successful attempts in the returned row: 1

## Status
**PASS — Expected counts observed**

## Conclusion
Splunk returned one matching row with three failed attempts and one successful attempt for the same username and source IP address.

## Scope and Limitations
This validates the observed sample-data scenario only. It does not establish production readiness or prove that the rolling time window is correct for every timestamp, event ordering, or real authentication source.
