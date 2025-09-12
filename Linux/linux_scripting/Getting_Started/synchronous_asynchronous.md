# Synchronous and Asynchronous Processing

- There are two primary modes of processing: synchronous and asynchronous.

## Synchronous Processing
- Sometimes referred to as **blocking**, is a traditional approach to scripting where tasks
are run <ins>sequentially</ins>.
- Each task is run one-by-one, in the order they're defined in a script.
- When a script encounters a time consuming operation, such as reading a large
file, the entire script is paused, or **blocked**, until it completes the operation.
- This can lead to inefficient resource usage and slower run times.

- Synchronous is useful when <ins>it's a predictable, and straightforward order of operations.</ins>
- Not well-suited for situations when parellelism is required.

<br>

## Asynchronous Processing

- Asynchronous processing <ins>allows tasks to run **independently** without blocking
the processing of the script.</ins>
- Instead of waiting for a task to complete, the script continues running other tasks.
- Results in more efficient resource utilization.

- Well-suited for tasks that have no dependencies with one another, and can be run in parallel.

> [!NOTE]
> Asynchronous code typically involves the use of callbacks (or promises) to manage the flow
> of operations.  

<br>

## Processing in Bash and Powershell
- In Bash and Powershell, synchronous processing is the default behavior.

> [!NOTE]
> One way of implementing asynchronous processing with Bash and Powershell is by
> using the **&** operator.  
> Asynchronous invocations are more scalable than synchronous invocations.

EXAMPLE:
```
./script.py &
./script2.py &
./script3.py &
```