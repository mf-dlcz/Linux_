# Retries and Backoff
Retry refers to the act of reattempting an operation after an initial failure.  
Use retries to handle transient failure, which are temporary errors that might resolve themselves when the operation is run again.
The purpose of retry is to increase the likelihood of successful completion of a task.

## Implementing Retries
- Define a variable to control the retry mechanism.

```
MAX_RETRIES=3
SLEEP_INTERVAL=5
RETRYABLE ERROR=1
```



