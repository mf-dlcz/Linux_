# Logging
- Enhances script reliability, helps with troubleshooting, and provides valuable
insights into your script operations.

## Logging to stdout and stderr
- Use **stdout** (standard output) and **stderr** (standard error) to handle regular
output and error messages.

### These examples redirect stdout and stderr messages to separate log files
- The **Write-Output** cmdlet logs a standard message to a file called **stdout_log.txt**

- The **Write-Error** cmdlet writes an error message to a file named **stderr_log.txt**

- For the last two lines of code, the pipeline operator **|** takes the output from the left 
command and uses it for input for the command on the right.

- You use the **Out-File** command to append output to a file. You use the **-Append**
parameter to append the message to the existing contents of the log file instead of overwriting it.

- Note the use of the redirection operator **2>&1** to redirect the standard error to the same
location as the standard output.

```
$stdoutLog = "stdout_log.txt"
$stderrLog = "stderr_log.txt"
Write-Output "This is a standard output message." | Out-File -Append $stdoutLog
Write-Error "This is an error message." 2>&1 | Out-File -Append $stderrLog
```

## Logging Functions
- With custom logging, you _can control where log messages are directed, the format of those messages,
and any additional actions you'd like to take when logging events._

<br>

In the following example we have a **Write-Log** function that takes a message, a log file path,
and a log level as parameters.  

You construct a log entry with a timestamp, log level, and log message.  

Finally, the script demonstrates the use of the **Write-Log** function with different log messages 
and levels. 

```
function Write-Log {
    param(
        [string]$Message,
        [string]$LogFile = "script_log.txt",
        [string]$LogLevel = "INFO"
    )
    $Timestamp = Get-Date -Format "yyyy-MM-dd HH:mm:ss"
    $LogEntry = "[$Timestamp] [$LogLevel] $Message"
    # Output to stdout
    Write-Output $LogEntry
    # Output to log file
    Add-Content -Path $LogFile -Value $LogEntry
}
# Example Usage:
Write-Log -Message "Script started."
Write-Log -Message "Processing data." -LogLevel "DEBUG"
Write-Log -Message "An error occurred!" -LogLevel "ERROR"
Write-Log -Message "Script completed."]r
```

> [!NOTE]  
> Common log levels on PowerShell include **INFO**, **WARNING**, **ERROR**, and **DEBUG**.

## Log Rotation
- Use log rotation to manage log files by limiting their size or quantity.

- Using log rotation ensures efficient use of storage space and makes it more convenient to 
analyze and maintain logs.

- In PowerShell, you can implement log rotation using a custom function that checks the size 
of a log file and rotates it when it reaches a specific threshold.

***

The following script checks for the size of the current log file and rotates it if it exceeds the
specified size.

```
$LogFilePath = "script_log.txt"
$MaxLogSizeMB = 1
if ((Get-Item $LogFilePath).length -gt ($MaxLogSizeMB * 1KB)) {
    $TimeSeconds = [int64](Get-Date -UFormat %s)
    Rename-Item $LogFilePath -NewName "script_log_$TimeSeconds.txt"
    Write-Output "Log rotated." $LogFilePath
}
```

## Centralized Logging
- Involves aggregating log data from multiple sources into a central repository or service.

- This streamlines log analysis, monitoring, and troubleshooting, especially in environments 
with multiple servers or distributed systems.

```
$syslogserver = "syslog.example.com"
$syslogport = 514
$syslogmessage = "Log message to be sent to syslog server"
Write-Host $syslogmessage | Send-Udpmessage -RemoteAddress $syslogserver -RemotePort $syslogport
```