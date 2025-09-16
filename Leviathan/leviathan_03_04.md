# Leviathan Level 3 -> 4

## 🧠 Goal  

Log into Leviathan 3 and find the password for Leviathan 4.  

---

## 🔐 Credentials  

- **Username:** `leviathan0`  
- **Host:** `leviathan.labs.overthewire.org`  
- **Port:** `2223` (SSH)  
- **Password:** `f0n8h2iWLP`  

---

## 🖥️ Commands Used  

```bash
# connect to leviathan0
ssh leviathan3@leviathan.labs.overthewire.org -p 2223

leviathan3@leviathan:~$ ls -l
total 20
-r-sr-x--- 1 leviathan4 leviathan3 18100 Aug 15 13:17 level3
leviathan3@leviathan:~$ ltrace ./level3
__libc_start_main(0x80490ed, 1, 0xffffd464, 0 <unfinished ...>
strcmp("h0no33", "kakaka")                                        = -1
printf("Enter the password> ")                                    = 20
fgets(Enter the password> msylhy
"msylhy\n", 256, 0xf7fae5c0)                                = 0xffffd23c
strcmp("msylhy\n", "snlprintf\n")                                 = -1
puts("bzzzzzzzzap. WRONG"bzzzzzzzzap. WRONG
)                                        = 19
+++ exited (status 0) +++

leviathan3@leviathan:~$ id
uid=12003(leviathan3) gid=12003(leviathan3) groups=12003(leviathan3)
leviathan3@leviathan:~$ ./level3
Enter the password> snlprintf
[You've got shell]!
$ whoami
leviathan4
$ id
uid=12004(leviathan4) gid=12003(leviathan3) groups=12003(leviathan3)
$ cat /etc/leviathan_pass/leviathan4
WG1egElCvO



```
___

## 💡 Theory
```bash

```
___

## 📤 Output
```bash
WG1egElCvO
```
