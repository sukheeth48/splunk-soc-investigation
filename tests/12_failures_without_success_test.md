# Failures Without Success Test

## Objective
Verify that the detection does not alert when repeated failures occur without a successful login.

## Test Scenario
- Username: `admin`
- Source IP: `192.0.2.41`
- Three failed login attempts.
- Zero successful login attempts.
- All events occur within the five-minute test window.

## Expected Result
`should_alert=NO`, because this detection requires at least three failures and one success within the configured window.

## Actual Result
- Failed attempts: 3
- Successful attempts: 0
- Detection result: `NO`

## Status
**PASS**

## Conclusion
The detection correctly withheld this specific alert because no successful login occurred. Repeated failures may still warrant investigation through a separate failed-login detection.

This test uses synthetic events and does not establish how a production environment behaves.
