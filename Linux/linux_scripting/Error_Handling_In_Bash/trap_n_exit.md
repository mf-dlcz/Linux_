# Trap and Exit

The **exit** command is useful for controlled script termination and providing exit status information to associated scripts or programs.  
The **exit** code can be any integer.  

```
exit [ EXIT_CODE ]
```

## Using the Trap Command
The **trap** command uses signal handlers, which are functions or commands that run in response to specific signals or conditions.  
This provides a way to customize how your script responds to events, such as errors.
```
trap 'commands' SIGNAL
```
<br>

```
#!/bin/bash

# Define a custom error handling function
handle_error() {
    echo "An error occurred. Exiting script."
    exit 1
}

# Set up a trap to run the error handling function on ERR signal
trap 'handle_error' ERR

# Simulate an error
non_existent_command
```