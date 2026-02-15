# Lab 5 — Linux System Awareness

## Objective
Demonstrate basic system awareness by reviewing logged-in users, active sessions, running processes, listening services, and host information on a Linux system during investigation.

## Environment
- Operating System: Ubuntu Linux
- Access Method: Local terminal

## Scope
This lab focuses on read-only system awareness activities commonly performed during Tier 1 SOC investigations. No system configuration changes were made.

## Investigation Summary
- Reviewed logged-in users and active sessions.
- Checked running processes for any obvious anomalies.
- Identified listening network services and associated ports.
- Confirmed system uptime and host information.

## Findings
- Logged-in users and sessions were expected and consistent with local usage.
- Running processes were standard system and user processes.
- SSH service was listening on port 22 as expected.
- No unexpected or suspicious network services were identified.
- System uptime, hostname, and OS information were consistent with a normal lab environment.

## Outcome
- No abnormal system activity identified.
- No escalation required.

## Evidence
- [Logged-in users (`who`)](./screenshots/linux_logged_in_users_who.png)
- [Active sessions (`w`)](./screenshots/linux_active_sessions_w.png)
- [Running processes (`ps aux`)](./screenshots/linux_running_processes_ps_aux.png)
- [Listening services (`ss -tulnp`)](./screenshots/linux_listening_services_ss_tulnp.png)
- [System info (`uptime`, `hostnamectl`)](./screenshots/linux_system_info_uptime_hostnamectl.png)
