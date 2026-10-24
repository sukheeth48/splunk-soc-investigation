# SOC Detection Test Matrix

## Detection Under Test
Repeated authentication failures followed by a successful login.

## Test Results

| Test ID | Scenario | Expected Behavior | Recorded Result | Status |
|---|---|---|---|---|
| DET-001 | 3 failures + 1 success | Alert | `should_alert=YES` | PASS |
| DET-002 | 2 failures + 1 success | No alert | `should_alert=NO` | PASS |
| TWIN-001 | Events within approximately 4 minutes | Alert | `should_alert=YES` | PASS |
| TWIN-002 | Failures 6–8 minutes before success | No alert | `should_alert=NO` | PASS |
| DET-004 | 3 failures + 0 successes | No alert from this rule | `should_alert=NO` | PASS |

## Test Environment
- SIEM: Splunk Cloud Search & Reporting
- Test data: Temporary synthetic events created with `makeresults`
- Detection grouping: Username and source IP
- Time-window test: Five-minute rolling window

## Coverage Notes
- Positive detection behavior was tested.
- Below-threshold behavior was tested.
- Absence of a successful login was tested.
- Within-window and outside-window behavior was tested.

## Limitations
These results cover the documented synthetic test scenarios only. They do not establish production detection effectiveness, test all possible event sequences, or prove malicious activity. The imported CSV validation is a separate test against the four-event sample dataset.

## Next Testing Priorities
- Test events from unrelated usernames and source IPs.
- Test out-of-order timestamps and boundary conditions.
- Validate against realistic Windows authentication logs.
- Configure and test a native Splunk alert.
