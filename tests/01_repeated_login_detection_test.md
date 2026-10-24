# Detection Test: Repeated Login Failures Followed by Success

## Test ID
DET-001

## Purpose
Verify that the detection rule flags a username and source IP combination with at least three failed logins and at least one successful login.

## Test Data
- Username: `admin`
- Source IP: `192.0.2.50`
- Failed login events: 3
- Successful login events: 1

## Expected Result
- The combination should match the detection rule.
- `failed_attempts` should equal 3.
- `successful_attempts` should equal 1.
- `severity` should equal `Investigate`.

## Actual Result
PASS — executed in Splunk using temporary test events. The query returned 3 failed attempts, 1 successful attempt, and `should_alert=YES`.

## Evidence
The positive test confirms that the configured threshold is met. The test used synthetic events created with `makeresults`; it did not modify the imported CSV dataset.

## Limitations
This test uses synthetic authentication events. It verifies the query's expected behavior on this sample, not detection effectiveness against real-world attacks.
