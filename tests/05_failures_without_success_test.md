# Detection Test: Failures Without Successful Login

## Test ID
DET-004

## Objective
Verify that the detection requiring repeated failures followed by a successful login does not trigger when no successful login exists.

## Test Data
- Username: `testuser`
- Source IP: `192.0.2.70`
- Failed authentication events: 3
- Successful authentication events: 0

## Expected Result
The detection should not trigger because the condition requires at least three failures and at least one success for the same username and source IP within the configured five-minute window.

## Current Status
DOCUMENTED — this test plan has not yet been executed in Splunk.

## Why This Matters
Repeated failures can be suspicious, but this particular detection is designed to identify a sequence that includes a subsequent successful login. Other detections may be appropriate for repeated failures without a success.

## Limitations
This test uses a synthetic scenario. A non-trigger from this rule does not mean the activity is harmless.
