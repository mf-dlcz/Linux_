# Logging
- Logging is an important record-keeping mechanism in Bash scripts.
- Logs capture information such as script start and end times, events, and errors.
- This data is useful for understanding script behavior during troubleshooting.
- You can also use logs as a debugging aid, providing insights into flow control, 
actions taken by the script, and much more.

## stdout and stderr
When you run a script there are two primary channels for output.

### stdout (standard output)
- Default channel where regular output is sent. It includes the normal, expected output for a command.

### stderr (standard error)
- This channel is specifically designed for error messages. 
- If something goes wrong while running the script or command, the error messages are sent to stderr.

***

One can capture both regular and error messages into a log file, because they can provide valuable information 
for debugging and monitoring.

```
#!/bin/bash

echo "Attempting to divide 10 by 0"
result=$((10/0))

echo "Result: $result"
```

***
- **2>** is the syntax used to redirect stderr output of a command or script.
```
./practice 2> error.log
```
<br>
<br>

## Logging Levels
- Logging levels are a way to categorize log messages based on their severity.

1. **CRITICAL**  
    - Use CRITCAL to log severe issues that can cause a script failure.
    - _Reserved for urgent errors that require immediate attention and intervention._

2. **ERROR**
    - Use ERROR to log error messages or any unexpected conditions that could impact your script's operation.

3. **WARN**
    - Use WARN to log information that might not be errors, but could lead to potential problems if not addressed.
    - It serves as a warning about conditions that might need further investigation.

4. **INFO**
    - Use INFO to log general information about the script's progress or key events.

5. **DEBUG**
    - Use DEBUG to log detailed information for debugging purposes.

> [!NOTE]   
> The logging levels follow a hierarchy where each level includes all the levels below it in terms of severity.

<br>

## Logging Functions
- Logging functions are functions that encapsulate the logic of recording messages at different levels of severity.

```
#!/bin/bash
LOG_FILE="script.log"
log_debug() {
    echo "$(date): DEBUG - $1" >> "$LOG_FILE"
}
log_info() {
    echo "$(date): INFO - $1" >> "$LOG_FILE"
}
log_warn() {
    echo "$(date): WARN - $1" >> "$LOG_FILE"
}
log_error() {
    echo "$(date): ERROR - $1" >> "$LOG_FILE"
}
# Simulate various log messages
log_info "Script started."
log_warn "Warning: Something unexpected happened."
log_error "Error: Critical issue occurred."
```
<br>

## Log Rotation
- Log rotation prevents log files from becoming too large.
- It envolved creating new files and archiving old ones, ensuring log sizes is manageable.



```
#!/bin/bash

MAX_LOG_SIZE=1000000
CURRENT_LOG_SIZE=$(wc -c < "script.log")

if [ "$CURRENT_LOG_SIZE" -gt "$MAX_LOG_SIZE" ]; then
    mv "script.log" "script.log.old"
    touch "script.log"
fi
```

<br>

## Centralized Logging
- In some circumstances, you might need to gather log data from multiple sources into a centralized location.
- This streamlines log analysis and monitoring across a distributed system.

<br>

- In the following example, you use scp (Secure Copy Protocol) to transfer your local log file (script.log) to a central log server (central-log-server).
- This is a basic example of centralized logging where you consolidate logs from various sources for streamlined analysis.

```
#!/bin/bash

CENTRAL_LOG_SERVER='central-log-server.com'
LOG_FILE='script.log'

# Secure Copy Protocal 
scp "$LOG_FILE" "#CENTRAL_LOG_SERVER:/path/to/central/logs/"
```