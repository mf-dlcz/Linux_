# Troubleshooting Overview
Scripts with errors can lead to unintended consequences, such as applications not working as expected, system instability and data loss.

## Troubleshooting Scripts
Involves analyzing errors, logs and script behavior to determine the root causes of problems.

- **Understanding error messages:** Interpret error messages, and exit codes to determine the nature of the issue.
- **Logging:** Use logging mechanisms to capture relevant information about your script performance, including errors.  
Analyzing logs can help identify patterns and recurring issues.
- **Reviewing Code:** Inspect your script's code to identify potential sources of errors, such as unhandled edge cases or incorrect assumptions.
- **Testing** Develop test cases that simulate various scenarios to validate how the script handles errors.  
Testing can help uncover hidden issues, and ensures that error handling works as expected.

## Common errors in scripting
Often revolve around syntax, logic, and file referencing errors.

### Syntax Errors
- Unclosed quotes or incorrect use of semicolons.Forgetting to close single or double quotes can lead to a syntax errors.
- Incorrect use of semicolons for command separation can also cause errors. Use semicolons to separate multiple commands on a single line, but don't forget spaces around them.
- Incorrectly referencing variables, such as missing the **$** sign, can result in errors.

### Logic and Conditional Errors
- Misusing conditional statements like if, elif, and fi, can cause errors.

### File and Directory Errors
- Attempting to work with files and directories that don't exist will lead to errors. Always check if a file or directory exists before referencing it in your script.

## Error Handling in Bash

### Error Handling and Exit Codes
Exit codes are numerical codes Bash scripts return to indicate the outcome of commands. Exit codes are an essential part of error handling.  
You can use exit codes to determine the success or failure of commands in your script.

- **0:** This is a standard exit code for successful processing of your code. When your script exits with code 0, it indicates that it ran without errors.
- **1-225:** Typically represents various error conditions. Exit code of **127** often indicates that a _command or script was not found._

### Using set -e to Check Exit Codes In Your Commands
The **set -e** option tells the script to exit immediately if any command returns an error(non-zero exit status).  
Think of it like a "stop on error" switch:  
with set -e:
```
#!/bin/bash
set -e          # Turn on "stop on error"
mkdir testfolder
cd wrongfolder      # This fails
echo "Hello"        # This never runs because script stopped at the error
```

### Using $? to Check Exit Codes in your Commands
Stores exit status of the most recently run command.  
You can access the exit status using **$?** and use it to make conditional decisions based on the outcome of a command.
```
#!/bin/bash

# Attempt to remove non-existent file
rm non_existent_file

# Check the exit code and perform custom error handling
if [ $? -ne 0 ]
then
   echo "Error: Failed to remove the file."
   # Add custom error handling actions here
else
   echo "File removed successfully"
fi

# Continue running script
echo "Script continues running after error handling"
```

> [!NOTE]  
> Use **$?** in situations where your command might fail, but you want the script to continue processing.  
> It's common to use a combination of both, where **set -e** is enabled for critical failures, and **$?** for partial failure tolerance.