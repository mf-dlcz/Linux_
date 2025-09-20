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