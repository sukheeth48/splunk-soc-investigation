# MITRE ATT&CK Mapping: Repeated Authentication Failures

## Detection Overview
This detection identifies at least three failed authentication attempts followed by at least one successful authentication for the same username and source IP in the imported sample dataset.

## Potential ATT&CK Technique
- **Technique:** T1110 — Brute Force
- **Tactic:** Credential Access
- **Reference:** https://attack.mitre.org/techniques/T1110/

## Why This Mapping Is Relevant
Repeated authentication failures may be consistent with password guessing or other brute-force behavior. A subsequent successful login can justify further investigation.

## Important Qualification
This is a potential behavioral mapping, not proof that brute-force activity occurred. The same pattern can arise from ordinary password-entry errors or automated processes using outdated credentials.

The current sample dataset contains synthetic events and does not identify a real attacker or establish malicious intent.

## Detection Evidence
- Failed attempts: 3
- Successful attempts: 1
- Username: `admin`
- Source IP: `192.0.2.50`
- Lab disposition: Investigate

## Future Improvement
Validate the detection against realistic authentication logs and add contextual evidence before assigning a more specific ATT&CK technique or concluding that an attack occurred.
