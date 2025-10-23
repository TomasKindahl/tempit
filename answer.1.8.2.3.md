# basic network commands

1.8.2.3. **PowerShell:** PowerShell is an entirely different business, test some of the commands on [MicroSofts Performing networking tasks](https://learn.microsoft.com/en-us/powershell/scripting/samples/performing-networking-tasks?view=powershell-7.5), namely:

|Command line|Description|
|-|-|
|List the IP addresses for your computer|`Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter IPEnabled=$true | Select-Object -ExpandProperty IPAddress`|
|Ping 8.8.8.8|`Get-CimInstance -Class Win32_PingStatus -Filter "Address='8.8.8.8'"`|
|Retrieve the IP addresses of DHCP servers|`Get-CimInstance -Class Win32_NetworkAdapterConfiguration -Filter  "IPEnabled=$true and DHCPEnabled=$true" |  Format-Table -Property DHCP*`|