## Get-NetDomain
Get currents user domain
![[image 4.png]]

## Get-NetForest
Get information about the forest the current user's domain is in:
![[image 5.png]]

## Get-NetForestDomain
Get all domains of the forest the current user is in:
![[image 6.png]]

## Get-NetDomainController

Get info about the DC of the domain the current user belongs to:
![[image 1.avif]]

## Get-NetGroupMember

Get a list of domain members that belong to a given group:
![[image 7.png]]

## Get-NetLoggedon

Get users that are logged on to a given computer:
![[image 8.png]]

## Get-NetForestTrust

Enumerate forest trusts from the current domain's perspective:
![[image 9.png]]

## Get-NetProcess

Get running processes for a given remote machine:

```
Get-NetProcess -ComputerName dc01 -RemoteUserName offense\administrator -RemotePassword 123456 | ft
```
![[image 2.avif]]

## Invoke-MapDomainTrust

Enumerate and map all domain trusts:
![[image 10.png]]

## Invoke-ShareFinder

Enumerate shares on a given PC - could be easily combines with other scripts to enumerate all machines in the domain:
![[image 11.png]]

## Invoke-UserHunter

Find machines on a domain or users on a given machine that are logged on:
![[image 12.png]]

all functions
```
Get-IPAddress
Convert-NameToSid
Convert-SidToName
Request-SPNTicket
Get-DNSZone
Get-DNSRecord
Get-NetDomain
Get-NetDomainController
Get-NetForest
Get-NetForestDomain
Get-NetForestCatalog
Get-NetUser
Get-UserEvent
Get-NetComputer
Get-ADObject
Set-ADObject
Get-ObjectAcl
Add-ObjectAcl
Invoke-ACLScanner
Get-GUIDMap
Get-NetOU
Get-NetSite
Get-NetSubnet
Get-NetGroup
Find-ManagedSecurityGroups
Get-NetGroupMember
Get-NetFileServer
Get-DFSshare
Get-NetGPO
Get-NetGPOGroup
Find-GPOLocation
Find-GPOComputerAdmin
Get-LoggedOnLocal
Invoke-CheckLocalAdminAccess
Get-SiteName
Get-Proxy
Get-LastLoggedOn
Get-CachedRDPConnection
Get-RegistryMountedDrive
Get-NetProcess
Invoke-ThreadedFunction
Invoke-UserHunter
Invoke-ProcessHunter
Invoke-EventHunter
Invoke-ShareFinder
Invoke-FileFinder
Invoke-EnumerateLocalAdmin
Get-NetDomainTrust
Get-NetForestTrust
Find-ForeignUser
Find-ForeignGroup
Invoke-MapDomainTrust
Get-DomainPolicy
```
