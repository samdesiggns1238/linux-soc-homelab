# Linux SOC Home Lab

## Overview
Personal cybersecurity home lab built to develop hands-on skills for a SOC Analyst role.
Environment runs on VirtualBox with Ubuntu 24.04 LTS.

## Lab Environment
- Host OS: Windows 11 Pro
- Virtualization: Oracle VirtualBox
- Guest OS: Ubuntu 24.04.4 LTS
- RAM allocated: 8GB
- Storage: 50GB

## Objectives
- Build practical Linux skills for SOC analysis
- Practice log analysis and file system investigation
- Simulate and investigate security scenarios
- Document findings as a working SOC analyst would

## Skills Developed
- Linux filesystem navigation
- User and permission analysis
- Log reading and interpretation
- Process monitoring and analysis
- System log investigation (syslog, dpkg.log, auth.log)
- Command chaining with pipe operator
- Filtering and searching logs with grep

## Investigations Completed
| Investigation | File/Area | Key Finding |
|---------------|-----------|-------------|
| /etc filesystem analysis | /etc/passwd, /etc/shadow, /etc/hosts | Identified system users and DNS mapping |
| Auth log grep analysis | /var/log/auth.log | Analyzed sudo usage and baseline CRON activity |
| Process analysis | ps aux output | Identified normal vs suspicious process indicators |

## Certifications in Progress
- Linux Essentials (Cisco NDG)
- AZ-900 Microsoft Azure Fundamentals
- SC-900 Microsoft Security Fundamentals
- CompTIA Security+
- SC-200 Microsoft Security Operations Analyst
