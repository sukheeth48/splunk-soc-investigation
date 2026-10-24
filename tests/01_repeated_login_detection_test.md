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
PASS — the sample dataset produced one matching result with three failures and one success.

## Limitations
This test uses synthetic authentication events. It verifies the query's expected behavior on this sample, not detection effectiveness against real-world attacks.
