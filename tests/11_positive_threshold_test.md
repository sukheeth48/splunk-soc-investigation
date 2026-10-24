# Positive Alert Threshold Test

## Objective
Verify that the authentication detection triggers when the configured threshold is met.

## Test Scenario
- Username: `admin`
- Source IP: `192.0.2.40`
- Three failed login attempts followed by one successful login.
- All events occur within the five-minute test window.

## Expected Result
The final successful login should produce `should_alert=YES` because the same username and source IP have three failures and one success within the detection window.

## Actual Result
- Failed attempts: 3
- Successful attempts: 1
- Final detection result: `YES`

## Status
**PASS**

## Conclusion
The detection correctly identified the tested sequence of repeated failures followed by a successful login.

This synthetic result demonstrates detection logic, not proof of a real brute-force attack.
