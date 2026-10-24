# Five-Minute Authentication Detection Dashboard Panel

## Purpose
Display authentication events that match the repeated-failure-and-success detection rule.

## Dashboard
`SOC Authentication Investigation`

## Panel Name
`Five-Minute Authentication Detection`

## Detection Conditions
- At least three failed login attempts.
- At least one successful login.
- Events grouped by username and source IP address.
- Events evaluated within a five-minute rolling window.

## Displayed Fields
- Event time
- Username
- Source IP address
- Failed attempts in the window
- Successful attempts in the window
- Severity

## Validation
The panel preview returned a matching row with three failures, one success, and severity `Investigate`.

## Limitations
This panel uses the current sample authentication dataset. The result validates the tested scenario, not production readiness. Real deployment requires checking timestamp accuracy, event ordering, data-source compatibility, and scheduled alert behavior.
