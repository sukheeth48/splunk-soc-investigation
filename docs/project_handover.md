# SOC Authentication Investigation — Project Handover

## Project Overview
This project demonstrates a Splunk-based authentication investigation using synthetic login events. It includes SPL queries, detection logic, validation tests, a dashboard, investigation documentation, and screenshots.

## Main Components

- `data/` — sample authentication events.
- `queries/` — SPL investigation and detection queries.
- `detections/` — detection logic and ATT&CK mapping.
- `tests/` — positive, negative, time-window, and event-isolation test documentation.
- `reports/` — validation reports and incident analysis.
- `playbooks/` — triage and investigation workflows.
- `evidence/` — screenshots of the Splunk dashboard.

## Detection Summary
The demonstration detection looks for at least three failed login attempts and at least one successful login within a five-minute rolling window, grouped by username and source IP.

## How to Review the Project
1. Read the root `README.md`.
2. Inspect the sample CSV in `data/`.
3. Review the reusable detection query in `queries/05_five_minute_auth_detection.spl`.
4. Read the test reports in `tests/`.
5. Review the dashboard screenshots in `evidence/`.
6. Read the incident and triage documents in `reports/` and `playbooks/`.

## Important Limitations
The project uses synthetic data and demonstrates a learning scenario. The current implementation has not been validated as a production detection. Before production use, validate timestamps, data-source compatibility, rolling-window behavior, alert scheduling, and response procedures.

## Handover Status
The repository contains documentation and evidence for the demonstrated authentication detection workflow.
