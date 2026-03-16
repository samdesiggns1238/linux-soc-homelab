# /etc Filesystem Analysis

## Objective
Investigate key configuration files in the /etc directory 
to understand system users, credentials, and network configuration.

## Environment
- OS: Ubuntu 24.04.4 LTS
- Tool: Linux terminal (bash)
- Date: March 2026

## Files Investigated

### /etc/passwd
**Command used:** `cat passwd`

**Purpose:** Contains a list of all system users, both real and service accounts.

**Format:** `username:x:UID:GID:description:home_directory:shell`

**Key finding:** Only users with UID 1000 or higher are real human users. 
All others are service accounts created by the system.

**SOC relevance:** A new user with UID 1000+ that doesn't belong 
could indicate an attacker created a backdoor account.

---

### /etc/shadow
**Command used:** Not accessed (requires root privileges)

**Purpose:** Stores hashed passwords for all system users.

**SOC relevance:** If an attacker gains access to this file, 
they can attempt to crack password hashes offline.

---

### /etc/hosts
**Command used:** `cat hosts`

**Purpose:** Local DNS mapping - resolves hostnames to IP addresses 
before querying external DNS servers.

**Key finding:** 127.0.0.1 maps to localhost (the machine itself).

**SOC relevance:** Attackers can modify this file to redirect 
legitimate domains to malicious servers - known as local DNS spoofing.

## Conclusions
The /etc directory contains critical configuration files that are 
common targets in post-exploitation scenarios. Monitoring changes 
to these files is essential for detecting unauthorized access.
