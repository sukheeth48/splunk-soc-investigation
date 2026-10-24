# SOC Investigation 01 — Suspicious Login Pattern

## 1. Objective

Investigate a simulated authentication sequence involving repeated failed login attempts followed by a successful login.

## 2. Environment

- SIEM: Splunk Cloud Platform
- Query language: Splunk Processing Language (SPL)
- Data source: Synthetic events generated using `makeresults`
- Account: `admin`
- Source IP: `192.0.2.50`

**Important:** These are simulated events, not real Windows security logs. The IP address is reserved for documentation and examples.

## 3. Findings

| Metric | Result |
|---|---:|
| Total authentication events | 4 |
| Failed logins | 3 |
| Successful logins | 1 |
| Time from first failure to success | 180 seconds |
| Investigation status | Investigate |

## 4. Analysis

Three failed login attempts occurred before a successful login for the same simulated username and source IP address. The first failure and successful login were three minutes apart.

This pattern may indicate password guessing or another authentication issue. However, the synthetic data does not establish that an actual attacker was present or that an account was compromised.

## 5. Recommended Next Steps

1. Validate the events against the original authentication logs.
2. Check whether the source IP and account are expected in the environment.
3. Review surrounding authentication events and the successful session.
4. Check for unusual activity after the successful login.
5. Escalate if additional evidence supports suspected compromise.

## 6. Limitations

This exercise demonstrates SPL searching, aggregation, event sequencing and basic detection logic. It does not demonstrate ingestion of real Windows logs, threat-intelligence enrichment, or a confirmed security incident.

## 7. Conclusion
The simulated login pattern meets the example threshold of three failures followed by a success and warrants further investigation. Additional evidence would be required to determine whether the activity is malicious.
