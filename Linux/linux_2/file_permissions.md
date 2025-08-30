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

<br>

## User File-Creation Mode Mask (Unmask)

**Default permissions** come from the _unmask_, subtracting permissions from the system's defaults

- Check the current unmask values
```
$ unmask
```

- Modify unmask values (default permissions)
```
$ unmask u=rwx, g=rx, o-rwx
```

The unmask has a default value of **0022** and affects the default permissions as follows:  


| Permissions Type |       Files     |   Directories   |
| :--------------: | :-------------: | :-------------: |
|  System default permissions | 666 |  777  |
|  unmask value |  022  |  022  |
|  Resulting permissions |  666 - 022 = 644  |  777 - 022 = 755  |
|  Symbolic form |  rw-r--r--  |  rwxr-xr-x  |