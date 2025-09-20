# Retries and Backoff

## Retries
- The process of re-attempting an operation multiple times to increase the chances
of success when transient errors occur.

***
You intentionally cause an error. The while loop is set to retry the operation up to
a maximum of $MaxAttempts times. Inside the try block, you attempt an operation. If 
successful, the break statement exits the loop immediately. If the operation fails, 
the catch block runs, logging the error and initiating a delay. The loop continues 
until the maximum number of attempts is reached or the operation is successful. 

```
$MaxAttempts = 3
$Attempt = 1

while ($Attempt -le $MaxAttempts) {
    try {
        # Attempt a connection to the application server
        $result = Invoke-RestMethod https://localhost:8088/info
        break  # Exit the loop if the operation is successful
    }
    catch {
        Write-Host "Attempt $Attempt failed: $_"
        $Attempt++
        Start-Sleep -Seconds 2  # Add a delay before the next attempt
    }
}
if ($Attempt -gt $MaxAttempts) {
    Write-Host "Operation failed after $MaxAttempts attempts."
}
```

## Exponential Backoff
- Is a strategy that introduces increasing delays between successive retry attempts
to reduce the load on systems during periods of high demand.

```
$MaxAttempts = 3
$Attempt = 1

while ($Attempt -le $MaxAttempts) {
    try {
        # Attempt a connection to the application server
        $result = Invoke-RestMethod https://localhost:8088/info
        break  # Exit the loop if the operation is successful
    }
    catch {
        Write-Host "Attempt $Attempt failed: $_"
        $Attempt++
        Start-Sleep -Seconds (2 * $Attempt)  # Exponential backoff
    }
}
if ($Attempt -gt $MaxAttempts) {
    Write-Host "Operation failed after $MaxAttempts attempts."
}
```