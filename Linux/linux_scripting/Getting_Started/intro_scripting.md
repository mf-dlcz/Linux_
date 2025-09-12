# Intro to Scripting

- Scripts help efficiently automate routine computing tasks.
- A script is like a recipe, offers a straightforward set of instructions to complete small, specific tasks.

> [!NOTE]
> A __shell__ refers to a computer program that gives you the ability to interact with an operating system's services.

## Scripting Use Cases

- **Automating File Backups**  
    - With scripting, one can schedule backups at specific intervals, or run them after specific events like a code deployment.

- **Monitoring Disk Space**  
    - Use scripting to enable real-time monitoring of available disk space on your servers or storage devices.  
    - Set thresholds to create alerts or actions when your disk space falls below a certain level.  
    - Generate reports or log events for historical analysis.
  
- **CI/CD**  
    - Automation scripts are crucial to streamline the building, testing, and deployment of application code.
    - Scripts run automated pipelines whenever code changes occur.
    - Scripts can also implement rollbacks and automated testing procedures to maintain code quality and application reliability.

- **Log File Rotation**
    - Use scripting to automate tasks such as compressing, archiving and deleting old log files.
    - This ensures that log files do not consume excessive disk space and are organized for convenient retrieval.

<br>

## Common Shell and Scripting Languages

### Bash - used on Linux and Mac OS

❎ Best for the following cases
- Compress and archive files for backup
- Filter, parse and insert log files into databases
- Schedule scripts to automate tasks
- Deploy scripts to perform system administration and maintenance

> [!NOTE]
> bash scripts use the .sh file extension  
> scripts written with bash start with a #!

### Powershell - Windows OS and built on .net

❎ Best for the following cases
- User account management
- Managing processes and services
- Registry key management
- Managing infrastructure as code

> [!NOTE]
> Powershell scripts use the .ps1 file extension. 
> Can either run interactively from the Powershell prompt
> or run directly like any executable.  
> Powershell uses a set of built-in commands known as cmdlets.  
> Cmdlets follow a standard verb-noun naming scheme.