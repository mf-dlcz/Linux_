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