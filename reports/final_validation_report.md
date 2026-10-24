# Final SOC Detection Validation Report

## Objective
Verify that the repeated-login detection matches the imported authentication dataset.

## Environment
- SIEM: Splunk Cloud Search & Reporting
- Source: Imported synthetic CSV dataset
- Sourcetype: `csv`

## Validation Results

| Metric | Observed Result |
|---|---:|
| Total events | 4 |
| Failed authentication events | 3 |
| Successful authentication events | 1 |
| Detection condition | Matched |

## Outcome
**PASS — DETECTION MATCHED**

The imported dataset satisfied the configured threshold: at least three failed attempts and at least one successful attempt for the same username and source IP.

## Interpretation
The query correctly identified the expected pattern in this sample dataset. This result validates the query against the four imported events; it does not prove a real attack occurred or establish production detection effectiveness.

## Next Improvements
- Test realistic Windows authentication logs.
- Add a time-window correlation.
- Test additional edge cases.
- Configure and verify a Splunk alert.
