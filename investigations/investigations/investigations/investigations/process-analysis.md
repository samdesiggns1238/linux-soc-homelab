# Process Analysis - SOC Investigation

## Objective
Learn to identify and analyze running processes on a Linux system
to detect suspicious activity.

## Environment
- OS: Ubuntu 24.04.4 LTS
- Commands used: ps aux, grep, kill, pipe |

## Commands Practiced

### ps aux
Lists all running processes on the system with detailed information.

**Columns explained:**
| Column | Meaning |
|--------|---------|
| USER | Who is running the process |
| PID | Process ID - unique identifier |
| %CPU | CPU usage |
| %MEM | Memory usage |
| START | When the process started |
| COMMAND | The program being executed |

### Combining ps aux with grep
Used to filter specific processes from the full list.

**Example:**
`ps aux | grep "root"` — shows only processes running as root
`ps aux | grep "ubuntu"` — shows only processes running as ubuntu user

## Key Findings

- PID 1 is always /sbin/init — the first process Linux starts
- All system processes have low PID numbers (1-100)
- Processes running as root with high PID numbers warrant investigation
- /tmp directory is a common location for malicious processes

## SOC Relevance
| Indicator | Normal | Suspicious |
|-----------|--------|------------|
| Process location | /usr/bin, /sbin, /bin | /tmp, /var/tmp |
| Process owner | root for system processes | Unknown user with root |
| PID number | Low for system processes | High PID with root and unknown name |
| Process name | Recognizable system names | Random characters or mimicking system names |

## Conclusions
ps aux combined with grep is a fast way to identify suspicious
processes during an incident investigation. Always check the
process location (COMMAND column) and the user running it.
