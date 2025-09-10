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

2. Use a while loop to check whether that value of the retries variable is less that the maximum number of retries you specified in the  
'MAX_RETRIES' variable. If the condition is met, the command will run.
<br>

3. The script checks the exit status of the command using **$?**. If the exit status is 0 (success), you use a break statement to exit the while loop.  
If the exit status of the command is not 0 (failure), the script proceeds to the 'else' block.
<br>

4.