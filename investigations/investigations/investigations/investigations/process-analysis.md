# Process Analysis - SOC Investigation

## Objective
Practice identifying and analyzing running processes on a Linux system
to develop skills for detecting suspicious activity during SOC investigations.

## Environment
- OS: Ubuntu 24.04.4 LTS
- Commands used: ps aux, grep, kill, pipe |

## What I Learned

### ps aux
Lists all running processes on the system with detailed information.
Each process shows the following information:

| Column | Meaning |
|--------|---------|
| USER | Who is running the process |
| PID | Process ID - unique number assigned to each process |
| %CPU | CPU usage percentage |
| %MEM | Memory usage percentage |
| START | When the process started |
| COMMAND | The program being executed |

### Combining ps aux with grep using pipe
I practiced filtering specific processes from the full list using the pipe operator.

`ps aux | grep "root"` — shows only processes running as root
`ps aux | grep "ubuntu"` — shows only processes running as the ubuntu user

## Key Findings

- PID 1 is always /sbin/init — the first process Linux starts at boot
- All core system processes have low PID numbers
- Processes running from /tmp are suspicious — legitimate programs run from /usr/bin or /sbin
- The pipe operator | allows chaining commands to filter large outputs efficiently

## SOC Relevance
| Indicator | Normal | Suspicious |
|-----------|--------|------------|
| Process location | /usr/bin, /sbin, /bin | /tmp, /var/tmp |
| Process owner | Known system users | Unknown user with elevated privileges |
| PID number | Low for system processes | High PID with root and unknown name |
| Process name | Recognizable system names | Random characters or names mimicking system processes |

## Conclusions
Using ps aux combined with grep allows me to quickly identify suspicious
processes during an incident investigation. The key indicators to check
are the process location, the user running it, and whether the process
name is recognizable.
ps aux combined with grep is a fast way to identify suspicious
processes during an incident investigation. Always check the
process location (COMMAND column) and the user running it.
