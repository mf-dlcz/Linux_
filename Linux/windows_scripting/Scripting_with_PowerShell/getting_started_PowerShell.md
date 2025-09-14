# Creating PowerShell Scripts
- There are many ways to create a PowerShell script file.
- Use **New-Item** cmdlet to create _files, directories, and other items._

Create a new folder (directory)
```
New-Item -ItemType File -Path "file_path\"
```

Use the **.ps1** extension
```
New-Item -ItemType File -Path "file_path\practice.ps1"
```
***

## Navigating to your Script Directory
Use **cd** to navigate to a different directory

```
cd C:\Users\Administrator\MyFiles
```

Use **.\** prefix to run the script
```
.\practice.ps1
```

## PowerShell Help
To get basic help use **Get-Help**
```
Get-Help <CmdletName>
```

Use **Get-Process** to receive a summary of the cmdlet, its syntax, parameters, and examples
```
Get-Help Get-Process
```

For more detailed info, use **-Detailed** or **-Full**. 
This gives you additional info, including parameter descriptions and examples.
```
Get-Help Get-Process -Full
```

```
Get-Help Get-Process -Detailed
```

Use the **-Name** parameter to search for cmdlets related to a specific keyword.
```
Get-Help -Name Keyword
```

If you have an internet connection, use **-Online** to open the online documentation for PowerShell.
```
Get-Help Get-Process -Online
```