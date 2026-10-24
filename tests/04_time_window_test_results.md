# Five-Minute Authentication Detection Test Results

## Objective
Evaluate the five-minute rolling-window detection using synthetic authentication events.

## Test Results

| Test | Scenario | Observed Result | Status |
|---|---|---|---|
| TWIN-001 | Three failures and one success within approximately four minutes | `should_alert=YES` | PASS |
| TWIN-002 | Three failures occur 6–8 minutes before the success | `should_alert=NO` | PASS |

## Interpretation
The within-window test demonstrated the expected positive behavior. The outside-window test demonstrated that the earlier failures were excluded from the final success event's five-minute rolling window.

## Environment
- Platform: Splunk Cloud Search & Reporting
- Method: Synthetic events generated with `makeresults`
- Correlation window: Five minutes
- Grouping: Username and source IP

## Limitations
These tests demonstrate behavior for the tested synthetic sequences only. They do not establish production detection effectiveness, validate all event-ordering cases, or prove malicious activity. Further testing with realistic authentication logs is required.

## Conclusion
Both documented time-window scenarios produced their expected results in the lab.
