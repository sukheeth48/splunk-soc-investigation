# Detection Test: Five-Minute Window Boundary

## Test ID
TWIN-003

## Objective
Observe how the five-minute rolling window handles a failure timestamped approximately five minutes before the successful authentication event.

## Test Scenario
- Three synthetic failures were placed at approximately -5, -4, and -3 minutes.
- One synthetic success was placed at the current time.
- The events used the same username and source IP.

## Observed Result
- Failures in window: 2
- Successes in window: 1
- `should_alert`: NO

## Interpretation
Splunk excluded the oldest failure from the final event's five-minute rolling window in this test. The remaining two failures did not meet the configured threshold of three.

## Validation Status
OBSERVED — the result was obtained from the synthetic boundary test. This records the behavior of this specific query and test sequence.

## Limitations
The test does not establish a universal rule for every time-window implementation. Boundary behavior should be verified against the exact query, event timestamps, and Splunk version used in a deployment.
