
# Auth Log Analysis

## Objective
Analyze authentication logs to identify normal vs suspicious 
activity on a Linux system.

## Environment
- OS: Ubuntu 24.04.4 LTS
- Log file: /var/log/auth.log
- Commands used: `tail -n 20 auth.log`, `cat auth.log`

## What is auth.log?
Records all authentication events on the system including:
- User logins and logouts
- sudo command usage (who ran what and when)
- SSH connection attempts
- Failed login attempts

## Key Observations

### Normal baseline activity
- CRON jobs appearing every 10 minutes - this is expected system behavior
- sudo events showing exact commands executed with timestamp and user

### SOC Relevance
| Event | Normal | Suspicious |
|-------|--------|------------|
| CRON execution | Every ~10 min | Unusual timing or new cron jobs |
| sudo usage | Known admin users | Unknown user running sudo |
| SSH login | From known IPs | Login from unknown country or IP |
| Failed logins | Occasional | Multiple failures = brute force |

## Conclusions
auth.log is one of the first files a SOC analyst checks during 
an investigation. Establishing a baseline of normal behavior 
is essential to detecting anomalies efficiently.
