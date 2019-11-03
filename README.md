# Get-DiskDriveInfo
A PowerShell script that retrieves all hard disk info via WMI/CIM calls.

It accepts multiple PC names from the command line.

![PC](/images/MultiplePCNames.JPG)

As well as the pipeline
`"Josh-LT-01" | Get-DiskDriveInfo.ps1` 

By default uses WMI but can also use CIM using the **-UseCIM** parameter.
![CIM](/images/CIM.JPG)

It also uses a *somewhat* accurate percentage of how much work is remaining.
![PC](/images/Percentage.JPG)

The script is also equipped with built in Active Directory support. The following parameters are available as well:
1. **-WorkstationsOnly** - *(Queries AD for all PCs that don't have the "Server" keyword in their OS attribute)* 
2. **-ServersOnly** - *(Queries AD for all PCs that DO have the "server" keyword in their OS attribute)*
3. **-SpecifyOU** - *(Reads in a specific OU and only grabs the computer names from there)*

By default the script will not output any files but the parameter **-OutputFile** is available for use.
![output](/images/Output.PNG)
