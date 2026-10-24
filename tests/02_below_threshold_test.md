# Detection Test: Below Failure Threshold

## Test ID
DET-002

## Purpose
Verify that the detection does not flag an account and source IP when the number of failed logins is below the configured threshold.

## Test Data
- Username: `testuser`
- Source IP: `192.0.2.60`
- Failed login events: 2
- Successful login events: 1

## Detection Condition
The detection requires at least 3 failures and at least 1 success for the same username and source IP.

## Expected Result
The test data should not match the detection condition because there are only 2 failures.

## Validation Status
PASS — executed in Splunk using temporary test events. The query returned 2 failed attempts, 1 successful attempt, and `should_alert=NO`.

## Evidence
The negative test confirms that the detection condition is not met when there are only two failures. The test used synthetic events created with `makeresults`; it did not modify the imported CSV dataset.

## Limitations
This is a synthetic test scenario. A result that does not trigger this particular rule does not prove that the activity is harmless; other detections may still be relevant.
