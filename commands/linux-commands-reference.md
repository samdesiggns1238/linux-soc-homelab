# Linux Commands Reference

Commands learned and practiced in the SOC home lab.
# Linux Commands Reference

Commands learned and practiced in the SOC home lab.

## Navigation Commands
| Command | Description | Example |
|---------|-------------|---------|
| pwd | Print working directory | pwd |
| whoami | Show current user | whoami |
| ls | List directory contents | ls /var/log |
| cd | Change directory | cd /etc |
| cat | Display file contents | cat hosts |
| tail | Display last lines of file | tail -n 20 auth.log |

## Search Commands
| Command | Description | Example |
|---------|-------------|---------|
| grep "word" file | Search for exact word (case-sensitive) | grep "Failed" auth.log |
| grep -i "word" file | Search ignoring uppercase/lowercase | grep -i "error" auth.log |

## Key Files Investigated
| File | Location | Purpose |
|------|----------|---------|
| passwd | /etc/passwd | List of all system users |
| shadow | /etc/shadow | Hashed passwords - root only |
| hosts | /etc/hosts | Local DNS mapping - target for DNS spoofing |
| auth.log | /var/log/auth.log | Authentication events and sudo usage |
