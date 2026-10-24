# SOC Detection Test Results

## Objective
Validate the threshold logic for the repeated login failures followed by success detection.

## Test Results

| Test ID | Scenario | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| DET-001 | 3 failures + 1 success | Alert | `should_alert=YES` | PASS |
| DET-002 | 2 failures + 1 success | No alert | `should_alert=NO` | PASS |

## Test Environment
- Platform: Splunk Cloud Search & Reporting
- Test method: Synthetic events generated with `makeresults`
- Detection threshold: At least 3 failures and at least 1 success for the same username and source IP

## Conclusion
Both threshold-logic tests passed. The detection triggered for the positive test and did not trigger for the below-threshold test.

## Limitations
These tests validate the threshold logic using temporary synthetic events. They do not establish the detection's effectiveness against real attacks or test every possible edge case. The imported CSV dataset is separate from these temporary test events.
