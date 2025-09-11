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
-