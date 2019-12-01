# Get-DiskDriveUsage
 
## Description
A PowerShell script that retrieves all hard disk info via WMI/CIM calls for multiple computers
and has Active Directory features.

## Updates
11/27/19: 
 - Change from a module to a single script.
 - Removed from function
 - Made return value simply the array of objects so it is not converted to table data.


## Installing the script
Install by typing in the below at an elevated PowerShell window:

`Install-Script -Name Get-DiskDriveUsage`
## Features
The script will get all hard drives usage for each computer:

![Usage](/images/EachDrive.PNG)

It accepts multiple PC names from the -ComputerName parameter as well as a text file with the -InputFile parameter:

`Get-DiskDriveUsage.ps1 -ComputerName Josh-LT-01, Josh-LT-01`

`Get-DiskDriveUsage.ps1 -InputFile "C:\Kits\Computers.txt"`

And the pipeline:

`"Josh-LT-01" | Get-DiskDriveInfo.ps1` 

By default uses WMI but can also use CIM using the **-UseCIM** parameter:

`Get-DiskDriveUsage -ComputerName Josh-LT-01, Josh-LT-01 -UseCIM`

It also uses a *somewhat* accurate percentage of how much work is remaining.
![PC](/images/Percentage.JPG)

The script is also equipped with built in Active Directory support. The following parameters are available as well:
1. **WorkstationsOnly** - *(Queries AD for all PCs that don't have the "Server" keyword in their OS attribute)* 
2. **ServersOnly** - *(Queries AD for all PCs that DO have the "server" keyword in their OS attribute)*
3. **SpecifyOU** - *(Reads in a specific OU and only grabs the computer names from there)*

By default the script will not output any files but the parameter **-OutputFile** is available for use.

`Get-DiskDriveUsage -ComputerName Josh-LT-01, Josh-LT-01 -OutputFile "C:\Kits\HardDriveInfo.csv"`
