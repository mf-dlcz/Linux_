# Find Files:

Most commands in Linux follow a set of syntax rules.
Command syntax is case-sensitive and generally comprises of the command itself, an option, and an argument.

**Command:** What you want Linux to do  
**Option:** How to modify the command  
**Argument:** What the command acts on  


## Displaying Files:

- **cat:** displays the contents of one or more files. Also, used to combine multiple files and display their contents.

- **head:** displays the first few lines of a file. By default, it shows the first 10 lines, but you can specify a different number of lines using the **-n** option.
    ``` 
    head -n 5 file.txt
    ```

- **more:** is a pager utility that displays the contents of a file one screen at a time. To navigate through the file use the keyboard command Enter (to scroll down one line), Space (to scroll down one page), Q (to quit).
    ```
    more file.txt
    ```

- **less:** is similar to more, but it provides more features and better navigation capabilities. You can use it to scroll up and down, search within the file, and even edit the file (if opened with the appropriate permissions).
    ```
    less file.txt
    ```

- **tail:** is used to display the last few lines of a file. By default, it shows the last 10 lines, but you can specify a different number of lines using the -n option.
    ```
    tail -n 20 file.txt
    ```
<br>

## Redirecting Data:
