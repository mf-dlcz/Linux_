# File Editing:

## Redirecting Data:
Linux has three standard streams of data:  
    - The **standard input**, or **stdin**  
    - The **standard output**, or **stdout**  
    - The **standard error**, or **stderr**  

Redirections are made through the greater than **(>)** and less than **(<)**  
operators and the file descriptor number.  
- **1>** redirects the standard output  
 You can use **>**  because 1 is the default numbers for this operator.  
- **2>** redirects the standard error.  
- **0<** redirects the standard input.  
You can use **<** because 0 is the default number.

***The double greater than operator (>>) appends data to a file.***

<br>

| Operator |                Description                 |               Existing File                |     New File   |
| :------: | :----------------------------------------: | :----------------------------------------: | :-------------:|
|     >    | Redirects output and overwrites the file.  | File contents are overwritten.             | File is created.
|     >>   | Redirects output and appends to the file.  | Output is appended to the end of the file. | file is created.

<br>

## Redirecting the Standard Output:

```
$command > file

$command 1> file
```
<br>

## Redirecting the Standard Error:

```
$command 2> file
```

<br>

## Redirecting the Standard Input:
```
$command < file
```

<br>

## Grep Command:
The grep command stands for Globally search for a Regular Expression and Print.  
It is used to search for patters or regular expressions within files or input streams.  

<br>

**SYNTAX**
-  **OPTION** parameter is a regular expression 
```
$ grep OPTIONS [PATTERN][INPUTFILE]
```

- Finds lines in **file.txt** that start with the word hello.
```
$ grep "^hello" file.txt
```

<br>

**EXAMPLES:**  
- Searches for the literal string "pattern" in the **file.txt** and prints the matching lines
```
$ grep "pattern" file.txt
```

<br>

<br>

## Piper Operator  (|)  
The pipe (|) operator creates a pipeline of programs by redirecting the flow of data from one program to another.  

This operator redirects the standard output but does not redirect the standard error flow of data.  
