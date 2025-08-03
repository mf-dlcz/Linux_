# Commands for Managing Files and Directories:


| Command |                Usage                     |
| :-----: | :--------------------------------------: |
|   pwd   | Displays the current working directory.  |
|   cd    | Changes the current working directory.   |
|   tree  | Displays the directory structure in a tree-like format. |
|   ls    | Lists the contents of a directory.   |
|   find  | Searches for files and directories in a directory structure. |
|   touch | Creates a new file or updates the timestamp of an existing file  |
|    cp   | Copies files and directories across locations.  |
|  mkdir  | Creates a new directory.  |
|    mv   | Moves or renames files and directory. |
|  rmdir  | Removes an empty directory.  |

<br>

## Examples of File & Directory Operations:

- **$** represents a regular user  

Check current working directory
```
$ pwd
```
RESULT = **/home/ec2-user**

<br>

Create a new directory and subdirectory
```
$ mkdir project && mkdir project/temp
```

Change to project directory using absolute path
```
$ cd /home/ec2-user/project
```

Move back up to the parent directory
```
$ cd ..
```

Change to project directory using relative path
```
$ cd project
```

Create new file in project directory
```
$ touch index.html
```

List contents of project directory
```
$ ls
``` 
**index.html**  
**/temp**

<br>

Move index.html to temp directory
```
$ mv index.html temp/
```

Find .html files in temp directory
```
find temp -name "*.html"
```
**temp/index.html**

<br>

Delete the entire temp directory
```
rm -rf temp/
```