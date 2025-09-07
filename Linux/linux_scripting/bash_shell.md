# Bash Shell Overview

- A Bash script is a plain text file containing a series of commands in the Bash programming language.
- Bash scripts are used to automate repetive tasks or run a sequence of commands on a Unix-like operating system.

## Creating a Bash script
1. Navigate to the desired directory using the **cd** command.
2. Use **touch** to create a new, empty file
```
touch practice
```
3. Open with the editor of choice
```
nano practice
```

- Bash scripts start with a _shebang_
- It's purpose is to provide a path to the intepreter indicating the location of the Bash shell in your system.
```
#!/bin/bash
```

4. sample script
```
#!/bin/bash
name="Pat Cindirella"
echo "Customer name is $name"
```

5. To execute the file run the following command.
```
chmod +x practice
```

> [!NOTE]  
> **chmod** stands for change mode in Unix-like operating systems, including Linux.

6. Run the script
```
./practice
```

## Bash Shell Elements

- **Variables** store data that can be referenced and manipulated from a Bash script or the command line.
- **Arrays** are variables that can hold multiple values. Can store and manipulate lists of items.
- **Loops** repeatedly run a series of commands.
- **Conditional** are control structures. Make decisions in your scripts based on certain conditions or criteria.
- **Functions** encapsulate a series of commands into a single reusable unit.