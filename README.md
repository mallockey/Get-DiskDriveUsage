# Get-DiskDriveInfo
A PowerShell script that retrieves hard disk info via WMI/CIM calls.

It accepts multiple PC names from the command line.

![PC](/images/MultiplePCNames.JPG)

As well as the pipeline
`"Josh-LT-01" | Get-DiskDriveInfo.ps1` 

By default uses WMI but can also use CIM using the -UseCIM parameter.
![CIM](/images/CIM.JPG)

It also uses a somewhat accurate percentage of how much work is remaining.
![PC](/images/images/Percentage.JPG)
