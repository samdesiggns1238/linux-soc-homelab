# Auth Log - Grep Analysis

## Objective
Practice using grep to filter specific events in auth.log.

## Commands Used
| Command | Purpose | Result |
|---------|---------|--------|
| grep "sudo" auth.log | Find all sudo usage | Found 2 sudo events by user ubuntu |
| grep "Failed" auth.log | Find failed logins | Found 1 Bluetooth service failure - not a login attempt |
| grep -i "error" auth.log | Find errors (case-insensitive) | No errors found - clean system |

## Key Findings
- No failed login attempts detected
- sudo used twice by user ubuntu on 2026-03-16 and 2026-03-17
- System baseline is clean with only CRON and normal service activity

## SOC Relevance
grep is the primary tool for filtering large log files quickly.
In a real SOC environment, auth.log can contain thousands of lines.
grep allows analysts to find specific events in seconds instead of reading manually.
