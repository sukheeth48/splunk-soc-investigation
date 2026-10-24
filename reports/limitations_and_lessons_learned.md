# SOC Authentication Investigation: Lessons Learned

## What I Built
- Imported a synthetic authentication dataset into Splunk Cloud.
- Wrote SPL queries to summarize login outcomes and identify repeated failures followed by a successful login.
- Created a dashboard to visualize authentication activity.
- Documented an investigation playbook.
- Tested the detection threshold with positive and negative synthetic test cases.

## What I Learned
- SPL can filter, aggregate, and summarize security events.
- Grouping by username and source IP helps identify related authentication activity.
- Detection thresholds must be tested to confirm expected behavior.
- Dashboards help analysts review event patterns.
- Investigation decisions should be based on evidence and context, not a single alert alone.

## Current Limitations
1. The dataset is small and synthetic.
2. The sample timestamps are hard-coded and do not represent live authentication activity.
3. The detection uses a simple threshold and does not include a configurable time-window correlation.
4. The rule does not verify whether the successful login belongs to the same session or whether the activity is authorized.
5. The lab does not demonstrate a live alert notification or automated incident response.

## Future Improvements
- Ingest realistic Windows authentication events from an authorized lab.
- Add a time-window-based correlation and test events outside that window.
- Investigate relevant Windows security event IDs.
- Test additional cases, including failures without a success and unrelated usernames or source IPs.
- Configure an alert in Splunk and validate its triggering behavior.
- Add sanitized investigation evidence and document false-positive analysis.

## Conclusion
This project demonstrates foundational Splunk searching, detection logic, dashboard creation, and test documentation. Further testing with realistic logs is needed before treating the rule as a production-ready detection.
