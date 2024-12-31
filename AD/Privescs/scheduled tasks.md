shell schtasks /query /fo LIST 2>nul | findstr TaskName
shell schtasks /query /tn "\Clean" /fo list /v
![[Pasted image 20241105192237.png]]
