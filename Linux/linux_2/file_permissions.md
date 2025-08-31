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
or
```
$ ls -l directory_name
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

<br>

## Special Permissions

The **sticky bit (+t)** is used to control file deletion within a directory.
- If set on a directory, only the file owner, directory owner, or root can delete or rename files.

<br>

- Set sticky bit using symbolic notation
```
$ chmod +t directory_name
```

- Set sticky bit using octal notation
```
$ chmod 1755 directory_name
```

The **set group ID (SGID) bit:**
- If set on a directory, new files inherit the group ID of the directory, rather than that of the
user who created the file.
- If set on an executable file, it runs with the permissions of the file's group owner.

<br>

- Set SGID bit using symbolic notation
```
$ chmod g+s directory_name
```

- Set SGID bit using octal notation
```
$ chmod 2755 directory_name
```

<br>

### Explanation of the command below:

stat = A command that displays file info  
-c = custom format  
%a = shows permissions in numeric format  
%A = shows permissions in a letter format

```
$ stat -c '%a %A' file_name
```
