# SOC Playbook: Repeated Login Failures Followed by Success

## 1. Objective
Investigate repeated failed authentication attempts followed by a successful login from the same source IP and username.

## 2. Alert Scenario
- Username: admin
- Source IP: 192.0.2.50
- Failed attempts: 3
- Successful attempts: 1
- Severity: Investigate

Note: These are synthetic lab events. This IP is reserved for documentation examples and is not evidence of a real attacker.

## 3. Investigation Steps
1. Confirm the username, source IP, timestamps, and authentication outcomes.
2. Check whether the failures occurred shortly before the successful login.
3. Review other login activity for the same account and source IP.
4. Determine whether the activity is expected or authorized, using approved internal context.
5. Record the evidence and investigation findings.

## 4. Possible Explanations
- A user repeatedly entered an incorrect password.
- An automated process used an outdated password.
- Someone attempted to guess a password and then successfully authenticated.

The available events alone cannot establish which explanation is correct.

## 5. Recommended Response
- If the activity is authorized, document the reason and close the alert according to team procedures.
- If suspicious, escalate to the incident response team and follow the organization's account-security procedures.
- Do not disable accounts or block IPs based only on this synthetic lab example.

## 6. Evidence to Record
- Username and source IP
- Event timestamps and outcomes
- Number of failed and successful attempts
- Related activity reviewed
- Investigation decision and justification

## 7. Lab Conclusion
The sample dataset meets the detection condition of at least three failures and at least one success for the same username and source IP. Additional context is required to determine whether the activity is malicious.
