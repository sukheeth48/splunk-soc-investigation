# Incident Case 001: Repeated Authentication Failures

## Case Summary
- **Case ID:** SOC-001
- **Detection:** Repeated login failures followed by a successful login
- **Account:** `admin`
- **Source IP:** `192.0.2.50`
- **Failed attempts:** 3
- **Successful attempts:** 1
- **Lab triage label:** Investigate
- **Case status:** Initial review documented

## Evidence Observed
The imported synthetic dataset contains four authentication events for the same username and source IP: three failures followed by one successful authentication.

The SPL detection query matched the configured condition of at least three failures and at least one success.

## Initial Assessment
This pattern can be consistent with repeated password-entry errors, an automated process using an outdated password, or attempted password guessing followed by a successful login.

The available sample events do not establish which explanation is correct. They also do not establish whether the successful login was authorized.

## Recommended Investigation
1. Review the event timestamps and confirm the sequence.
2. Examine surrounding authentication events and relevant account activity.
3. Check approved organizational context to determine whether the source and login are expected.
4. Document supporting evidence before deciding whether to close or escalate the case.

## Recommended Disposition
**Investigate further.** Do not classify the activity as a confirmed compromise based only on this sample. Escalation or containment should follow the organization's incident response procedures and require appropriate supporting evidence.

## Evidence Limitations
- All events are synthetic lab data.
- `192.0.2.50` is reserved for documentation examples.
- The dataset contains only four events and does not provide real endpoint, identity-provider, or network context.

## Analyst Conclusion
The detection behaved as expected against the sample dataset. Further contextual evidence would be required to determine whether similar activity in a real environment represents a security incident.
