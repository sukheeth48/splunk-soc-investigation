# SOC Authentication Detection — Test Summary

## Project Objective
Validate a Splunk detection that identifies three or more failed login attempts followed by at least one successful login for the same username and source IP within a five-minute rolling window.

## Test Results

| Test | Expected Result | Observed Result | Status |
|---|---|---|---|
| Three failures followed by success | Alert | `YES` | PASS |
| Two failures followed by success | No alert | `NO` | PASS |
| Three failures without success | No alert from this detection | `NO` | PASS |
| Events outside the five-minute window | No alert | `NO` | PASS |
| Different source IP addresses | Do not combine counts | `NO` | PASS |
| Different usernames | Do not combine counts | `NO` | PASS |
| Chronological event ordering | Correct rolling-window evaluation | `YES` for qualifying sequence | PASS |
| Five-minute boundary scenario | Only qualifying in-window failures count | `NO` | PASS |

## Detection Logic
- Group events by username and source IP address.
- Evaluate events in chronological order.
- Count failures and successes within the configured five-minute rolling window.
- Trigger this detection when failures are at least three and successes are at least one.

## Limitations
- Tests use synthetic events rather than real authentication logs.
- Passing these tests does not prove the detection is production-ready.
- The detection does not cover every brute-force or password-spraying scenario.
- Production deployment requires validation against the actual log source, timestamp handling, event ordering, and alert scheduling.

## Overall Result
**PASS — All documented synthetic scenarios produced their expected results.**

## Next Steps
1. Review the detection SPL for production suitability.
2. Validate the logic against a realistic authentication dataset.
3. Configure and test a scheduled alert if supported by the Splunk environment.
4. Document alert ownership, triage steps, and escalation criteria.
