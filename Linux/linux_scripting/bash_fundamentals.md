# Bash Fundamentals

- Variables are like containers that hold any kind of data.
- They store information that one can use in commands and expressions.
- There are two types of variables:
    - system (environment) variables
    - user-defined variables

## System Variables
- Built-in variables created and maintained by the Linux operating system.

## User-Defined Variables
- Are created by the user.
- These variables are used to store custom data or values specific to ones script.

> !NOTE
> **Capitalization in system-defined variables**
> In Bash, system-defined variables are typically defined in capital letters.

## Variables
- Ensure there are **no** spaces on either side of the equal sign. 
- Variables include letters, underscores, and digits.
- Names of variables are case-sensitive, and cannot include spaces.

```
varname="value"
```

- To envoke a variable reference its name prefixed with the **$** sign.
- To print a message with the variable's value use **echo**

```
#!/bin/bash
name="Maria"
vehicle="Rivian"
echo "Customer name is $name. $name has a $vehicle."
```

## Arrays
- Declaring an array involves listing elements inside parentheses.
- To access elements in an array reference their indices.

```
#!/bin/bash

favorite_colors=("grey" "burgandy" "orange" "lavander" "black" "brown")
echo ${favorite_colors[1]}          #outputs: burgandy
```