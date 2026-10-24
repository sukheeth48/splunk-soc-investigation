# Detection 01 — Repeated Failed Logins Followed by Success

## Purpose

Identify a username and source IP combination with at least three failed authentication attempts and at least one successful authentication event in the simulated dataset.

## Detection Logic

- Group events by username and source IP.
- Count failed authentication attempts.
- Count successful authentication attempts.
- Flag combinations with at least three failures and one success.

## Example Threshold

`failed_attempts >= 3 AND successful_attempts > 0`

The threshold is a learning example and must be validated against normal authentication activity before production use.

## Expected Test Case

| Username | Source IP | Failures | Successes | Expected Result |
|---|---|---:|---:|---|
| admin | 192.0.2.50 | 3 | 1 | Investigate |

## Suggested Severity

**Initial priority: Medium — Investigate**

This is a suggested triage priority for the lab, not a calibrated production severity rating. Real severity depends on account privileges, source context, timing and corroborating evidence.

## Analyst Response

1. Validate the original authentication events.
2. Check whether the source IP is expected.
3. Review related authentication activity.
4. Determine whether the successful session is legitimate.
5. Escalate if additional evidence supports compromise.

## False-Positive Considerations

- A user may mistype a password repeatedly.
- A service or application may retry authentication.
- An administrator may be testing account access.
- A legitimate user may successfully log in after several failures.

## Limitations

The current project uses synthetic events generated through SPL. This document describes the detection logic; it is not an automatically scheduled Splunk alert.

## Validation Status

Validated against the project's four-event simulated example only. Not yet validated against real Windows authentication logs.
