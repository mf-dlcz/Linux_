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

### For loops have three expressions
- **initialization**
- **condition**
- **update**