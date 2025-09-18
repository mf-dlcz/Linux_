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
