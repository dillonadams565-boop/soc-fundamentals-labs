# Lab 3 — Linux Authentication Log Review

## Objective
Review Linux authentication logs to identify failed and successful authentication events and understand what normal login activity looks like from a SOC perspective.

## Environment
- Operating System: Ubuntu Linux
- Log Source: /var/log/auth.log

## Scope
This lab focuses on local and SSH authentication activity only. Controlled failed login attempts, a successful login, and a privilege escalation event were generated and reviewed.

## Events of Interest
- Failed SSH authentication attempts
- Successful SSH authentication
- Privilege escalation using sudo

## What Was Done
- Located and reviewed the Linux authentication log file.
- Generated multiple failed SSH login attempts using incorrect credentials.
- Performed a successful SSH login using valid credentials.
- Executed a command using sudo to generate a privilege escalation log entry.

## What Was Observed
- Multiple failed authentication entries were recorded close together in time for the same user account.
- A successful authentication entry confirmed a valid login.
- Sudo activity was logged, showing the user, command executed, and successful privilege escalation.
- The events observed were consistent with normal user behaviour during testing.

## SOC Interpretation
A small number of failed authentication attempts followed by a successful login is typical of normal user activity. In a SOC environment, repeated failed logins, failures across multiple accounts, or authentication attempts from remote or unknown sources would warrant further investigation. Monitoring sudo activity is important for detecting unauthorized privilege escalation.

## Evidence
- Screenshot of failed SSH authentication entries in auth.log
- Screenshot of successful SSH authentication entry
- Screenshot of sudo privilege escalation log entry
