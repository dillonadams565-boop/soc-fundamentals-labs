# Lab 4 — SOC Alert Triage and Shift Handover

## Objective
Demonstrate Tier 1 SOC alert triage by reviewing a failed SSH authentication alert, documenting investigation findings, determining outcome, and recording shift handover notes.

## Alert Details
- Alert Type: Multiple failed SSH authentication attempts
- Affected Host: Ubuntu Linux
- Log Source: /var/log/auth.log

## Investigation Summary
- Reviewed Linux authentication logs for failed SSH login events.
- Identified repeated failed authentication attempts targeting an invalid user account.
- Confirmed source address and authentication method.
- Checked for any successful authentication related to the failed attempts.

## Findings
- Multiple failed SSH authentication attempts occurred within a short time period.
- Attempts targeted a non-existent user account.
- Source address was localhost (::1), consistent with controlled lab activity.
- A successful SSH login for a valid user account was observed separately and was expected.
- No evidence of unauthorized access was identified.

## Outcome
- Classification: Benign activity
- Action Taken: No escalation required

## Rationale
- Source and behaviour matched expected local testing activity.
- No indicators of compromise or malicious access were observed.
- Activity did not meet escalation thresholds.

## Shift Handover Notes
- Reviewed alert for failed SSH authentication attempts.
- Activity confirmed as benign (local testing).
- No further action required unless pattern or source changes.

## Evidence
- [Failed SSH authentication logs](../03-authentication-logs/linux/screenshots/linux_failed_ssh_logins.png)
- [Successful SSH authentication logs](../03-authentication-logs/linux/screenshots/linux_successful_ssh_login.png)

