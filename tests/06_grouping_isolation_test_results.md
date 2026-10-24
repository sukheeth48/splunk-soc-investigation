# Detection Test: Account and Source IP Isolation

## Objective
Verify that authentication events are grouped by both username and source IP.

## Test A: Different Usernames
- Username `admin`: 3 failures, 0 successes
- Username `testuser`: 0 failures, 1 success
- Expected: Neither group triggers the detection
- Observed: Both groups returned `should_alert=NO`
- Status: PASS

## Test B: Different Source IPs
- `admin` from `192.0.2.80`: 3 failures, 0 successes
- `admin` from `192.0.2.81`: 0 failures, 1 success
- Expected: Neither group triggers the detection
- Observed: Both groups returned `should_alert=NO`
- Status: PASS

## Interpretation
The tested SPL logic grouped events by `username` and `src_ip`. It did not combine failures and successes from different account/IP combinations.

## Test Environment
- Platform: Splunk Cloud Search & Reporting
- Method: Temporary synthetic events generated with `makeresults`

## Limitations
These tests validate the grouping logic for the scenarios tested. They do not prove that the detection is effective against real attacks or that every possible event sequence has been tested.
