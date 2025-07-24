# Shell Variables

- Shell Variables are used to store and manipulate data.  
- They can be used to pass information between commands and scripts and to configure the shell environment.  

### Variable Syntax
- Different types of values such as strings, numbers, or special chars can be stored in a shell variable.
- It's standard practice to use **lowercase letters, numbers and underscores.**  
<br>

EXAMPLE:  
```
$ name=value  
```

### Displaying Shell Variables
Use **echo** to view the value assigned to a variable. 

EXAMPLE:
```
$ echo $name
```

## Environment Variables
- Environment variables are a set of dynamic values that store system-wide or user specific configuration settings.
- They're used to pass information processes and scripts.
- Linux comes with several built-in environment variables that are predefined and serve different purposes.

### Common Environment Variables
- Displays the user's home directory
```
$HOME
```

- Stores the users current Linux shell type
```
$SHELL
```

- Stores the current user's username. Used to reference the username in logs, alerts and messages.
```
$USER
```

- Specifies a set of directories where executable programs are located.
```
$PATH
```

## Aliases
- Shorthand command that can be used for a longer command or sequence of commands.
- Aliases are defined in the **.bashrc** shell configuration file.

### Defining an Alias
- This command creates an alias called **'ll'**
```
$ alias ll='ls -l'
```

### Unalias
- If you need to remove an alias that was created use the unalias command.

```
$ unalias ll
```