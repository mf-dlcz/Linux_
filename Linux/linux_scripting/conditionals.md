# Conditionals
- Used to make decisions and control the flow of the scripts based on certain conditions.

## If Statements
```
if [ condition ]
then
[ block of code to run if condition is true ]
fi
```

> !NOTE
> The space before and after a **[ ]** construct are important for proper syntax and interpretation of the command.
> Spaces are necessary to distinguish this construct from other parts of the command.

```
#!/bin/bash

num=5

if [ $num -eq 5 ]
then
    echo "Number is 5"
fi
```

### Combining Logical Operators
- **&&** (logical AND)  
- **||** (logical OR)  

```
#!/bin/bash
num=2
if [ $num -ge 1 ] && [ $num -le 10 ]
then
    echo "Number is between 1 and 10"
fi
```

## If - Else Statements

```
if [ condition ]
then
    [ block of code to run if condition is true ]
else
    [ block of code to run if condition is false ]
fi
```
<br>

```
#!/bin/bash
num=6
if [ $num -eq 5 ]
then
    echo "Number is 5"
else
    echo "Number is not 5"
fi
```

## Else If (elif)

```
if [ condition ]
then
    [ block of code to run if condition is true ]
elif [ condition2 ]
then
    [ block of code to run if condition2 is true ]
elif [ condition3 ]
then
    [ block of code to run if condition3 is true ]
else
    [ block of code to run if none of the conditions are true ]
fi
```

<br>

```
#!/bin/bash

num=8

if [ $num -eq 5 ]
then
    echo "Number is 5."
elif [ $num -eq 10 ]
then 
    echo "Number is 10"
else
    echo "Number is neither 5 nor 10."
fi
```