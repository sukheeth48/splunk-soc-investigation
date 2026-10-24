# Event Ordering Test Results

## Objective
Verify that the authentication detection evaluates events in chronological order.

## Test Scenario
- Username: `admin`
- Source IP: `192.0.2.95`
- Three failed login events occurred before a successful login.
- All four events occurred within a five-minute window.

## Expected Result
The successful login should trigger the detection because three failures and one success occurred within the configured time window.

## Actual Result
- Failed attempts in the window: 3
- Successful attempts in the window: 1
- Detection result: `YES`

## Status
**PASS**

## Conclusion
The synthetic test passed when events were sorted chronologically before applying the five-minute rolling-window calculation.

This validates the tested scenario only; it does not establish that every possible event-ordering or production authentication scenario is covered.
