# SOC Analyst L1: Alert Triage Workflow

## Objective
Provide a repeatable workflow for investigating repeated authentication failures followed by a successful login.

## Step 1: Receive the Alert
- Review the alert name and detection condition.
- Record the account, source IP, event count, and time range.
- Confirm the alert came from the intended Splunk search.

## Step 2: Validate the Evidence
- Search for the related authentication events.
- Confirm the number of failures and successes.
- Check the timestamps and event sequence.
- Verify that the events belong to the same username and source IP.

## Step 3: Gather Context
- Review surrounding login activity.
- Check whether the account and source are expected using authorized internal records.
- Look for relevant endpoint, identity, or network evidence when available.

## Step 4: Assess Risk
Consider:
- Number and frequency of failed attempts
- Whether a successful login followed the failures
- Whether the account is privileged
- Whether the source or login pattern is unusual
- Whether additional evidence supports or contradicts suspicious activity

Do not conclude that an account is compromised from the failure count alone.

## Step 5: Choose a Disposition
- **Expected activity:** Document the evidence and close according to team procedures.
- **Suspicious or unclear activity:** Escalate for further investigation.
- **Strong evidence of compromise:** Follow the organization's incident response and containment procedures.

## Step 6: Document and Handover
Record:
- Alert and case identifiers
- Relevant timestamps and event details
- Searches performed
- Evidence reviewed
- Decision and reasoning
- Recommended next action

## Lab Limitations
This workflow is documented for a synthetic Splunk lab. It does not demonstrate a live alerting pipeline, real user verification, or actual incident containment.
