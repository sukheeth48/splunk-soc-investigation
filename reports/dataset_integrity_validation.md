# Authentication Dataset Integrity Validation

## Objective
Verify that the imported authentication CSV contains the expected number and types of events.

## Validation Query
```spl
index=* sourcetype=csv
| stats
    count AS total_events
    count(eval(event_action="failure")) AS failed_attempts
    count(eval(event_action="success")) AS successful_attempts
    dc(username) AS unique_usernames
    dc(src_ip) AS unique_source_ips
```

## Expected Results
- Total events: 4
- Failed attempts: 3
- Successful attempts: 1
- Unique usernames: 1
- Unique source IP addresses: 1

## Status
**PASS — Observed results matched the expected dataset.**

## Conclusion
The imported sample authentication dataset passed the basic integrity checks for event totals, login outcomes, usernames, and source IP addresses.

## Limitations
This validates the small synthetic dataset only. It does not establish the completeness, accuracy, or reliability of a production authentication log source.
