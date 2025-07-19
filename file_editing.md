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

| Item |                In Stock                    |               Existing File                |     New File   |
| :--: | :----------------------------------------: | :----------------------------------------: | :-------------:|
| >    | Redirects output and overwrites the file.  | File contents are overwritten.             | File is created.
| >>   | Redirects output and appends to the file.  | Output is appended to the end of the file. | file is created.
