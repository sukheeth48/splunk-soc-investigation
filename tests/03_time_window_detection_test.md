# Detection Test: Time-Window Correlation

## Test ID
DET-003

## Objective
Test whether repeated authentication failures followed by a successful login occur within a defined time window.

## Proposed Detection Window
Five minutes.

## Test Scenarios

### Scenario A: Events Within the Window
- Three failed login events occur within five minutes.
- A successful login follows within the same five-minute window.
- Expected result: Flag the sequence for investigation.

### Scenario B: Events Outside the Window
- Three failed login events occur over a much longer period.
- The successful login occurs outside the configured correlation window.
- Expected result: Do not flag this sequence using the five-minute correlation rule.

## Current Status
DOCUMENTED — these scenarios are test plans only. They have not yet been executed against a time-window-based detection query.

## Why This Matters
A time-window condition can make authentication detections more relevant by focusing on events that occur close together.

## Limitations
A five-minute window is a starting point for this lab, not a universally correct threshold. Production detection windows should be evaluated against the environment's normal authentication patterns and detection requirements.
