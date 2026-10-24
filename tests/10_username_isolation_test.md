# Username Isolation Test

## Objective
Verify that authentication events for different usernames are evaluated independently.

## Test Scenario
- Shared source IP: `192.0.2.30`
- Username `admin`: two failed login attempts.
- Username `guest`: one failed login attempt followed by one successful login.
- All events occur within the five-minute test window.

## Expected Result
Neither username should trigger an alert because neither independently meets the detection threshold.

## Actual Result
- `admin`: 2 failures, 0 successes, alert `NO`.
- `guest`: 1 failure, 1 success, alert `NO`.

## Status
**PASS**

## Conclusion
The test confirmed that events are grouped by username and source IP address. Failed attempts belonging to different usernames are not combined to trigger an alert.

This result applies to the synthetic test scenario.
