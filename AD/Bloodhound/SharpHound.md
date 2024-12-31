If you are on a machine that is a member, but you are authenticated as a local user, but have credentials for a domain user, get a shell for that user like so:

attacker@victim

```
runas /user:spotless@offense powershell

// if machine is not a domain member
runas /netonly /user:spotless@offense powershell
```

```
. .\SharpHound.ps1
Invoke-BloodHound -CollectionMethod All -JSONFolder "c:\experiments\bloodhound"
```

