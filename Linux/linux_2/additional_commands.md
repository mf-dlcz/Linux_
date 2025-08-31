# Additional Commands
<br>

## Nice and Renice Commands

- The "nice level" represents how much CPU usage a process is willing to give up to other processes
- The **nice** command starts a new process with a specific priority level
- The **renice** command changes the priority of a running process

<br>

Initialize priority of script.py to 5
```
$ nice -n 5 python.py
```

Change priority of PID 1234 to 10
```
$ renice -n 10 -p 1234
```

<br>

## Commands for Monitoring Active Processes
<br>

|    Command  |  Scale of a process |
| :---------: | :-----------------: |
| top | Displays real-time information about running processes and system usage (CPU, memory, etc.) |
| ps  | Displays information about processes currently running |
| pstree | Displays processes in a tree format to show parent-child relationships |
| pidof | Retrieves the process ID(s) of a running program |
| pgrep | Searches for processes matching a pattern and retrieves their process IDs |
| kill | Sends signals to processes to terminate or manage their execution |

<br>

## Network Interfaces and Addresses
Most Linux servers have two network interfaces:
1. **Loopback interface ->** Used by the Linux server for internal communication
    - Listed as **lo** in the output from Linux networking commands
2. **Ethernet interface ->** Used by the Linux server to connect to other devices and users on the network
    - Listed as **eth0** (or **en0**) in the output from Linux networking commands

There are two types of IP addresses used for Linux servers:
1. **IPv4 ->** Uses a 32-bit addressing scheme (for example, 203.0.113.0)
2. **IPv6 ->** Uses a 128-bit addressing scheme (for example, 2001:db8:0:1234:0:567:8:1)