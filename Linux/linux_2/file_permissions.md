# Basic Linux Permissions

Permissions for files and directories in Linux are:
- Granted to the user(owner), **group**. and **others**
- Categorized into **read (4)**, **write (2)**, and **execute (1)** permissions
- Represented as an octal (644) or in symbolic form (rw-r--r--)

If permissions for files and directories are 644 and 755 (respectively), then:

| Principal |       Files     |   Directories   |
| :-------: | :-------------: | :-------------: |
|  User(owner) | rw- (6) |  rwx (7)  |
|  Users in the same group as the file |  r-- (4)  |  r-x (5)  |
|  All other users |  r-- (4)  |  r-x (5)  |

<br>

List all files/folders with permissions
```
$ ls -la directory_name
```
