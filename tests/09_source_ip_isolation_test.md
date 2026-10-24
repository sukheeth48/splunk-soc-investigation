# Source IP Isolation Test

## Objective
Verify that failed login attempts from different source IP addresses are counted independently.

## Test Scenario
- Username: `admin`
- IP address `192.0.2.10`: two failed login attempts.
- IP address `192.0.2.20`: one failed attempt followed by one successful login.
- All events occur within the five-minute test window.

## Expected Result
Neither IP address should trigger an alert because neither independently meets the threshold of three failures and one success.

## Actual Result
- `192.0.2.10`: 2 failures, 0 successes, alert `NO`.
- `192.0.2.20`: 1 failure, 1 success, alert `NO`.

## Status
**PASS**

## Conclusion
The test confirmed that the detection groups events by username and source IP address, preventing attempts from separate IP addresses from being combined to meet the alert threshold.

This result applies to the synthetic test scenario.
