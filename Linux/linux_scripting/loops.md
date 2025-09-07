# Loops

1. **For loop** - Iterates over a list of items or values & run a set of commands for each item on the list.
2. **Until loop** - Runs a set of commands as long as a specific condition remains **false**.
3. **While loop** - Runs a set of commands as long as a specific condition remains **true**.

<br>

## For Loop
- **do** keyword marks the beginning of a code block that will be run repeatedly.
- **done** keyword marks the end of a code block.
- Iterates over a list of values, list of files, list of strings, or list of numbers.

```
for <variable> in <list>
do
<command>
done
```
***

### EXAMPLE 1:  
```
#!/bin/bash
for i in $(seq 1 10)
do
    echo $i
done
```

### EXAMPLE 2:
- **{}** specify a range of numbers.  
. _The code below prints numbers from 10 to 20_
```
#!/bin/bash
for i in {10..20}
do
    echo $1
done
```

### For loops with three expressions
- **initialization** sets an initial value of a loop variable
- **condition** is evaluated before each iteration of the loop. If condition expression is _true_ the loop runs. If the condition is _false_ the loop terminates.
- **update** (increment/decrement) runs at the end and it's responsible for updating the loop control variable in each iteration. It can be an increment or a decrement operation.

```
#!bin/bash
for ((i=1 ;i<=5; i++))
do
    echo "Iteration $i"
done
```

<br>

## While Loops
Runs a code block as long as a condition remains _true_.

```
while [ condition ]
do
[commands to be run in each iteration]
done
```

> !NOTE
> Comparison Operators in Bash  
> -lt (less than)  
> -le (less than or equal to)  
> -ge (greater than or equal to)  
> -gt (greater than)


<br>

## Until Loops
Runs a code block as long as a condition remains _false_.

```
until [ condition ]
do
[commands to be run in each iteration]
done
```

<br>

***

## Scheduling A Script
Format for scheduling scripts  
```
***** /path/to/script.sh
```

**minutes, hours, days, months, and weekdays.**

```
15 20 * 9 1-7 /path/to/hello_world.sh
```

> !NOTE  
> **15** at 15 minutes past  
> **20** at 20:00 (8:00 PM)  
> **\***  day of month (* means every day)  
> **9** month (September)  
> **1-7** days of week (Monday through Sunday)