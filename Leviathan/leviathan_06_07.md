# Leviathan Level 6 -> 7

## 🧠 Goal  

Log into Leviathan 6 and find the password for Leviathan 7.  

---

## 🔐 Credentials  

- **Username:** `leviathan6`  
- **Host:** `leviathan.labs.overthewire.org`  
- **Port:** `2223` (SSH)  
- **Password:** `szo7HDB88w`  

---

## 🖥️ Commands Used  

```bash
# connect to leviathan6
ssh leviathan6@leviathan.labs.overthewire.org -p 2223
leviathan6@leviathan:~$ ls -l
total 16
-r-sr-x--- 1 leviathan7 leviathan6 15036 Aug 15 13:17 leviathan6
leviathan6@leviathan:~$ ./leviathan6
usage: ./leviathan6 <4 digit code>
leviathan6@leviathan:~$ ./leviathan6 1234
Wrong
leviathan6@leviathan:~$ ltrace ./leviathan6
__libc_start_main(0x80490dd, 1, 0xffffd464, 0 <unfinished ...>
printf("usage: %s <4 digit code>\n", "./leviathan6"usage: ./leviathan6 <4 digit code>
)                                                                           = 35
exit(-1 <no return ...>
+++ exited (status 255) +++
leviathan6@leviathan:~$ gdb -q ./leviathan6
Reading symbols from ./leviathan6...
(gdb) set disassembly-flavor intel
(gdb) disassemble main
Dump of assembler code for function main:
   0x080491c6 <+0>:     lea    ecx,[esp+0x4]
   0x080491ca <+4>:     and    esp,0xfffffff0
   0x080491cd <+7>:     push   DWORD PTR [ecx-0x4]
   0x080491d0 <+10>:    push   ebp
   0x080491d1 <+11>:    mov    ebp,esp
   0x080491d3 <+13>:    push   ebx
   0x080491d4 <+14>:    push   ecx
   0x080491d5 <+15>:    sub    esp,0x10
   0x080491d8 <+18>:    mov    eax,ecx
   0x080491da <+20>:    mov    DWORD PTR [ebp-0xc],0x1bd3
   0x080491e1 <+27>:    cmp    DWORD PTR [eax],0x2
   0x080491e4 <+30>:    je     0x8049206 <main+64>
   0x080491e6 <+32>:    mov    eax,DWORD PTR [eax+0x4]
   0x080491e9 <+35>:    mov    eax,DWORD PTR [eax]
   0x080491eb <+37>:    sub    esp,0x8
   0x080491ee <+40>:    push   eax
   0x080491ef <+41>:    push   0x804a008
   0x080491f4 <+46>:    call   0x8049040 <printf@plt>
   0x080491f9 <+51>:    add    esp,0x10
   0x080491fc <+54>:    sub    esp,0xc
   0x080491ff <+57>:    push   0xffffffff
   0x08049201 <+59>:    call   0x8049080 <exit@plt>
   0x08049206 <+64>:    mov    eax,DWORD PTR [eax+0x4]
   0x08049209 <+67>:    add    eax,0x4
   0x0804920c <+70>:    mov    eax,DWORD PTR [eax]
   0x0804920e <+72>:    sub    esp,0xc
   0x08049211 <+75>:    push   eax
   0x08049212 <+76>:    call   0x80490a0 <atoi@plt>
   0x08049217 <+81>:    add    esp,0x10
   0x0804921a <+84>:    cmp    DWORD PTR [ebp-0xc],eax
   0x0804921d <+87>:    jne    0x804924a <main+132>
   0x0804921f <+89>:    call   0x8049050 <geteuid@plt>
   0x08049224 <+94>:    mov    ebx,eax
   0x08049226 <+96>:    call   0x8049050 <geteuid@plt>
   0x0804922b <+101>:   sub    esp,0x8
   0x0804922e <+104>:   push   ebx
   0x0804922f <+105>:   push   eax
   0x08049230 <+106>:   call   0x8049090 <setreuid@plt>
   0x08049235 <+111>:   add    esp,0x10
   0x08049238 <+114>:   sub    esp,0xc
   0x0804923b <+117>:   push   0x804a022
   0x08049240 <+122>:   call   0x8049070 <system@plt>
   0x08049245 <+127>:   add    esp,0x10
   0x08049248 <+130>:   jmp    0x804925a <main+148>
   0x0804924a <+132>:   sub    esp,0xc
   0x0804924d <+135>:   push   0x804a02a
   0x08049252 <+140>:   call   0x8049060 <puts@plt>
   0x08049257 <+145>:   add    esp,0x10
   0x0804925a <+148>:   mov    eax,0x0
   0x0804925f <+153>:   lea    esp,[ebp-0x8]
   0x08049262 <+156>:   pop    ecx
   0x08049263 <+157>:   pop    ebx
   0x08049264 <+158>:   pop    ebp
   0x08049265 <+159>:   lea    esp,[ecx-0x4]
   0x08049268 <+162>:   ret
End of assembler dump.
(gdb) 
```

FOCOUS ON MOST IMPORTANT PART 
```
   0x080491da <+20>:    mov    DWORD PTR [ebp-0xc],0x1bd3
```
```
   0x0804921a <+84>:    cmp    DWORD PTR [ebp-0xc],eax
   0x0804921d <+87>:    jne    0x804924a <main+132>
   0x0804921f <+89>:    call   0x8049050 <geteuid@plt>
   0x08049224 <+94>:    mov    ebx,eax
   0x08049226 <+96>:    call   0x8049050 <geteuid@plt>
```
compare between [ebp-0xc] which has value 0x1bd3 and eax if equal u get the euid
0x1bd3 = 1101111010011 = 7123
(1BD3)₁₆ = (1 × 16³) + (11 × 16²) + (13 × 16¹) + (3 × 16⁰) = (7123)₁₀

if not equal it will jump to main+132
```
   0x0804924a <+132>:   sub    esp,0xc
   0x0804924d <+135>:   push   0x804a02a
   0x08049252 <+140>:   call   0x8049060 <puts@plt>
```
(gdb) x/s 0x804a02a
0x804a02a:      "Wrong"

```
leviathan6@leviathan:~$ ./leviathan6 7123
$ cat /etc/leviathan_pass/leviathan7
qEs5Io5yM8
$ 
```
```
┌──(amro㉿amro)-[~]
└─$ ssh leviathan7@leviathan.labs.overthewire.org -p 2223
leviathan7@leviathan:~$ ls -l
total 4
-r--r----- 1 leviathan7 leviathan7 178 Aug 15 13:17 CONGRATULATIONS
leviathan7@leviathan:~$ cat CONGRATULATIONS
Well Done, you seem to have used a *nix system before, now try something more serious.
(Please don't post writeups, solutions or spoilers about the games on the web. Thank you!)
```
___


## 💡 Theory
```
watch assembly with nasm x86 32bit 
YOUTUBE:olivestem
```
___

## 📤 Output
```bash
qEs5Io5yM8
```
