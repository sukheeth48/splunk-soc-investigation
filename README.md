# SOC Investigation Using Splunk

A beginner-friendly Security Operations Center (SOC) lab demonstrating authentication-event analysis, SPL queries, basic detection logic, dashboard visualizations, and incident documentation.

## Project Objectives

- Analyze authentication events using Splunk Search & Reporting.
- Count failed and successful login attempts.
- Investigate authentication sequences and event timelines.
- Detect username and source-IP combinations with repeated failures followed by success.
- Visualize authentication activity in a Splunk dashboard.
- Document findings and investigation limitations.

## Tools Used

- Splunk Cloud Platform — search, analysis and visualization
- Splunk Processing Language (SPL) — investigation queries
- GitHub — source control and project documentation
- CSV — sample authentication dataset

## Investigation Scenario

The lab uses four synthetic authentication events for the `admin` account:

- Three failed login attempts.
- One successful login.
- All events share the documentation-reserved source IP `192.0.2.50`.
- The successful login follows the failures in the sample sequence.

The example detection threshold is at least three failures and at least one success for the same username and source IP.

## Repository Structure

```text
splunk-soc-investigation/
├── data/
│   └── sample_authentication_events.csv
├── queries/
│   ├── 01_login_investigation_summary.spl
│   └── 02_imported_login_detection.spl
├── detections/
│   └── 01_repeated_failures_then_success.md
├── reports/
│   ├── 01_login_investigation.md
│   └── dashboard_documentation.md
└── README.md
```

## How to Reproduce the Investigation

1. Import `data/sample_authentication_events.csv` into Splunk.
2. Select the appropriate time range, such as All time for this static dataset.
3. Run the queries in the `queries/` directory.
4. Verify the failure and success counts.
5. Review the authentication sequence and dashboard panels.
6. Read the investigation report and detection limitations.

## Expected Findings

| Metric | Sample result |
|---|---:|
| Total events | 4 |
| Failed logins | 3 |
| Successful logins | 1 |
| Elapsed time from first failure to success | 3 minutes |
| Suggested action | Investigate |

## Dashboard

The `SOC Authentication Investigation` dashboard contains panels for:

- Login outcomes.
- Failed logins by username.
- Login activity over time.

## Limitations

All records are synthetic and intended for training. The project does not establish a real account compromise, and the example threshold is not calibrated for production use.

The current version demonstrates basic SPL analysis and visualization. It does not yet implement a scheduled alert or a production detection pipeline.

## Future Improvements

- Ingest real Windows Security events from a controlled lab.
- Add additional authentication and endpoint event types.
- Improve field extraction and timestamp validation.
- Test detection thresholds against a larger dataset.
- Add investigation evidence and false-positive analysis.

## Author

SOC Analyst learning portfolio project.
