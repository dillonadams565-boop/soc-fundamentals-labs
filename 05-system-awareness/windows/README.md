# Lab 5 — Windows System Awareness

## Objective
Demonstrate basic system awareness by reviewing logged-in users, active sessions, running processes, listening network services, and host information on a Windows system during investigation.

## Environment
- Operating System: Windows
- Access Method: Local system access

## Scope
This lab focuses on read-only system awareness activities commonly performed during Tier 1 SOC investigations. No system configuration changes were made.

## Investigation Summary
- Reviewed logged-in user context and active sessions.
- Checked running processes using Task Manager.
- Identified listening network services and associated ports.
- Confirmed system information and uptime.

## Findings
- Logged-in user and sessions were expected.
- Running processes were standard Windows system and user processes.
- Listening network services were consistent with normal system behaviour.
- System information and uptime were consistent with a normal workstation.

## Outcome
- No abnormal system activity identified.
- No escalation required.

## Evidence
- [Logged-in user (`whoami`)](./screenshots/windows_logged_in_user_whoami.png)
- [Active sessions (Task Manager – Users tab)](./screenshots/windows_active_sessions_task_manager_users.png)
- [Running processes (Task Manager)](./screenshots/windows_running_processes_task_manager.png)
- [Listening services (`netstat -ano`)](./screenshots/windows_listening_services_netstat.png)
- [System info (`systeminfo`)](./screenshots/windows_system_info_systeminfo.png)
