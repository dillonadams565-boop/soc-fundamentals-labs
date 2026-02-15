# Lab 3 — Linux Authentication Log Review

## Objective
Review Linux authentication logs to identify failed and successful login activity from a SOC perspective.

## Environment
- Operating System: Ubuntu Linux
- Log Source: /var/log/auth.log

## Scope
This lab focuses on local and SSH authentication activity only. Failed login attempts, a successful login, and sudo activity were generated and reviewed on the host system.

## Events of Interest
- Failed SSH authentication attempts
- Successful SSH authentication
- Privilege escalation using sudo

## What Was Done
- Reviewed the Linux authentication log file.
- Generated multiple failed SSH login attempts using an invalid user.
- Performed a successful SSH login using a valid user account.
- Ran a command with sudo to generate a privilege escalation event.

## What Was Observed
- Multiple failed authentication entries occurred close together in time for the same invalid user.
- A successful authentication entry confirmed a valid SSH login.
- Sudo activity was logged, showing the user, command executed, and escalation to root.
- The activity observed was consistent with expected behaviour during controlled testing.

## SOC Interpretation
A small number of failed authentication attempts followed by a successful login is typical of normal user behaviour. In a SOC environment, repeated failed logins, failures across multiple accounts, or authentication attempts from unknown or external sources would warrant further investigation. Sudo activity should be monitored to detect potential misuse of elevated privileges.

## Evidence
- [Failed SSH authentication attempts](screenshots/linux_failed_ssh_logins.png)
- [Successful SSH authentication](screenshots/linux_successful_ssh_login.png)
- [Privilege escalation via sudo](screenshots/linux_sudo_activity.png)
