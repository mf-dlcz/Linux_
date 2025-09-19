# Conditional Execution
- **$?** provides an effective way to check if a command ran successfully or encountered
an error.

```
Get-Content "NonexistentFile.txt"

if ($?) {
    Write-Host "Command succeeded."
} else {
    Write-Host "Command failed."
}
```

## Controlling Scripts response to errors
- **$ErrorActionPreference** is a variable that determines how PowerShell responds to non-terminating
errors.
- The value of **ErrorActionPreference** can be set to different preferences, influencing 
whether errors are silently ignored, displayed, or treated as terminating errors.

### Values used for $ErrorActionPreference
- **Stop** makes all errors terminating. If an error occurs, PowerShell will stop running the
script or command.

- **Continue** makes non-terminating errors visible, but the script continues to run. This is the
default value of **$ErrorActionPreference**

- **Silently Continue** suppresses non-terminating errors. The errors are not displayed, and the script
continues running.

- **Inquire** prompts the user for action on each non-terminating error.

```
$ErrorActionPreference = 'Inquire'
# Command that may fail
Get-Content "NonexistentFile.txt"
# Check if the last command succeeded using $?
if ($?) {
    Write-Host "Command succeeded."
} else {
    Write-Host "Command failed."
}
```