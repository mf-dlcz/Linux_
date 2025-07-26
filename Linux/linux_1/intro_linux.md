# Intro to Linux:
- Operating systems act as an intermediary between computer hardware and software applications.  

## Roles and Functions of an OS
- **Resource Management:** Allocates and manages system resources like CPU, memory, disk space and external devices.  
- **File System:** Provides file management functionality for organizing, storing and retrieving data from storage devices.  
- **UI:** Provides a GUI or CLI for users to interact with the system and it's apps.  

## Advantages of Linux:

- **Open source** Doesn't need to purchase license.
- **Modular**  Option to download only the modules needed.
- **Extensible** Ability to modify and extend its functionality by contributing their own code.
- **Community Support** Access to various forums to resolve issues.

## Architecture:

💡 Linux OS is made up of user space and a kernel space.

- The **kernel** is made up of the core operating system functionality and acts  
as the bridge between the software and hardware components.

- The **user space** is the area where the applications and programs run on the OS.

### Linux File System:

💡 The Linux file system is a hierarchical structure.

- **GENERAL FILES:** 
    - Examples:
        - Image files
        - Program files
        - Text files  

- **DIRECTORY FILES:**
    - Examples:
        - /usr
        - /etc
        - /home

- **DEVICE FILES:**
    - Examples:
        - /dev/sda1
        - /dev/sda2


## Directory Structure

- The root directory (**/**) contains every other directory in the Linux operating system.
- The **/bin** directory contains compiled programs (binaries) ready to run.
- The **/lib** directory contains libraries needed by programs in **/bin**.
- The **/home** directory contains a home folder for each user.
- The **/usr** directory contains user applications and files.
- The **/tmp** directory is used for temporary files that will be deleted when the system is restarted.
- The **/var** directory contains variable data files. For example, log files are written to the /var/log directory.
- The **/boot** directory contains files like the kernel needed to boot the system.
- The **/etc** directory contains system configuration files.