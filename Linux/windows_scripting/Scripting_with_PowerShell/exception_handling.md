# Exception Handling Statements
- Error handling usually involves **try, catch, finally,** and **exit** statements.

***
- **try** block encapsulate code prone to errors.

- **catch** blocks manage error responses.

- **finally** runs code whether an exception occurs in the **try** block.

- **exit** stops the script with a specific exit code upon encountering an issue.

## Try and Catch
- The **try** and **catch** blocks are fundamental techniques for gracefully handling
exceptions in PowerShell scripts.

- The **try** block usually contains code that might cause an error.
- If the **try** block runs correctly, it skips over the catch.

- The **catch** block specifies the code to run if an error occurs.
- The **catch** block only runs if there's a terminating error.

```
try {
   # Code that may generate error
}
catch {
   # Code to handle the error
}
```

<br>

```
try {
    $result = 10 / 0 # This division by zero will cause an error
    Write-Host "Result: $result"
}
catch {
   Write-Host "An error occurred: $_"
}
```

## Finally
- Use **finally** block to specify code that runs regardless of whether an exception happened
in the **try** block.

- Often **finally** is used for cleanup operations or tasks that need to run regardless of the
error status.

- The **finally** block is optional.

```
try {
   # Code that may generate an error
}
catch {
   # Code to handle the error
}
finally {
   # Code that always runs
}
```

## Exit
- The **exit** command can be used within **try/catch** or **try/catch/finally** statements
to explicitly terminate the execution of a script when an exception occurs, based on a specific exit code.

- Typically, exit codes are placed within the **catch** block; however, if you need to perform cleanup before
exiting, _it is a good practice to move the exit command to the finally block to ensure that the cleanup code
executes, regardless of whether an exception occurred._

```
try {
    # Code that may generate an error
}
catch {
    # Exit with an error exit code
    exit 1
}
```
- Exit code of 1, signals a general error or exception.
- Any **exit** code greater than 1 can represent specific error conditions defined by the developer or
application.