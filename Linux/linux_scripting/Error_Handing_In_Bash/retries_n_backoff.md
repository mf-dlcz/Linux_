# Retries and Backoff
- Retry refers to the act of reattempting an operation after an initial failure.  
- Use retries to handle transient failure, which are temporary errors that might resolve themselves when the operation is run again.  
- The purpose of retry is to increase the likelihood of successful completion of a task.

## Implementing Retries
- Define a variable to control the retry mechanism.
- Sleep interval pauses the program for 5 seconds before trying again when something goes wrong.  
Each time it fails, it waits 5 seconds before trying again.
- Tells the program which problems are worth trying again to fix!

```
MAX_RETRIES=3
SLEEP_INTERVAL=5
RETRYABLE ERROR=1
```

## Template for a Basic Retry Mechanism
1. Initialize a variable named retries that is set to 0. This variable will keep track of how many times the operation is retried.
<br>

2. Use a while loop to check whether that value of the retries variable is less that the maximum number of retries you specified 
in the 'MAX_RETRIES' variable. If the condition is met, the command will run.
<br>

3. The script checks the exit status of the command using **$?**. If the exit status is 0 (success), you use a break statement 
to exit the while loop. If the exit status of the command is not 0 (failure), the script proceeds to the 'else' block.
<br>

4. In the else block, the script increments the retries variable by 1, which keeps track of the number of retry attempts made 
so far.
<br>

5. Use the sleep command to introduce a pause in the script for the number of seconds specified in the 'SLEEP_INTERVAL' 
variable. This introduces a delay between retry attempts to avoid overwhelming the system.
<br>

6. After the done statement, the script checks if the maximum number of retries has been reached. If this number is reached, it
prints a message and exits with a status code of 1. This indicates that it was unable to complete the task after the maximum allowed
retries.
<br>

```
MAX_RETRIES=5               # Maximum number of times to try
SLEEP_INTERVAL=3            # Wait 3 seconds between tries
RETRYABLE_ERROR=1           # Error code that says "okay to try again"

retries=0                   # Start counting our tries from zero

while [ $retries -lt $MAX_RETRIES ]; do         # Keep trying as long as we haven't hit max tries
    # Try to check if aws.amazon.com is up using the -I flag
    curl -I https://aws.amazon.com
    
    if [ $? -eq 0 ]; then                       # If it worked ($? means "did it work?")
        break                                   # Stop trying - we succeeded!
    else                                        # If it didn't work:
        retries=$((retries + 1))                # Count this try
        sleep $SLEEP_INTERVAL                   # Wait 3 seconds before trying again
    fi
done

# After we're done trying:
if [ $retries -eq $MAX_RETRIES ]; then          # If we tried 5 times and still failed
    echo "Maximum retry attempts reached. Exiting script."      # Tell the user
    exit 1                                      # Exit with an error
fi
```

## Backoff