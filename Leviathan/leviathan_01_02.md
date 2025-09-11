# Leviathan Level 1 -> 2

## 🧠 Goal  

Log into Leviathan 1 and find the password for Leviathan 2.  

---

## 🔐 Credentials  

- **Username:** `leviathan1`  
- **Host:** `leviathan.labs.overthewire.org`  
- **Port:** `2223` (SSH)  
- **Password:** `3QJ3TgzHDq`  

---

## 🖥️ Commands Used  

```bash
# connect to leviathan1
ssh leviathan1@leviathan.labs.overthewire.org -p 2223

leviathan1@leviathan:~$ ls -la
total 36
drwxr-xr-x   2 root       root        4096 Aug 15 13:17 .
drwxr-xr-x 150 root       root        4096 Aug 15 13:18 ..
-rw-r--r--   1 root       root         220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root       root        3851 Aug 15 13:09 .bashrc
-r-sr-x---   1 leviathan2 leviathan1 15084 Aug 15 13:17 check
-rw-r--r--   1 root       root         807 Mar 31  2024 .profile
leviathan1@leviathan:~$ strings ./check
td8 
/lib/ld-linux.so.2
_IO_stdin_used
puts
__stack_chk_fail
system
getchar
__libc_start_main
printf
setreuid
strcmp
geteuid
libc.so.6
GLIBC_2.4
GLIBC_2.34
GLIBC_2.0
__gmon_start__
secr
love
password: 
/bin/sh
Wrong password, Good Bye ...
;*2$"0
GCC: (Ubuntu 13.3.0-6ubuntu2~24.04) 13.3.0
crt1.o
__abi_tag
__wrap_main
crtstuff.c
# and so on 

leviathan1@leviathan:~$ cat /etc/leviathan_pass/leviathan2
cat: /etc/leviathan_pass/leviathan2: Permission denied
leviathan1@leviathan:~$ ./check cat /etc/leviathan_pass/leviathan2
password: sds
Wrong password, Good Bye ...
leviathan1@leviathan:~$ ltrace ./check
__libc_start_main(0x80490ed, 1, 0xffffd464, 0 <unfinished ...>
printf("password: ")                                         = 10
getchar(0, 0, 0x786573, 0x646f67password: 
)                            = 10
getchar(0, 10, 0x786573, 0x646f67
)                           = 10
getchar(0, 2570, 0x786573, 0x646f67
)                         = 10
strcmp("\n\n\n", "sex")                                      = -1
puts("Wrong password, Good Bye ..."Wrong password, Good Bye ...
)                         = 29
+++ exited (status 0) +++
leviathan1@leviathan:~$ ./check
password: sex
$ whoami
leviathan2
$ cat /etc/leviathan_pass/leviathan2
NsN1HwFoyN

```
___

## 💡 Theory
```bash
ltrace is used to see what library calls are made during binary execution
Library calls are, when a program calls a function from a file that is shared by multiple programs
for example, checking if the input is the correct password can be done with a library function 
strcmp is a standard C library function used to compare two null-terminated strings
```
___

## 📤 Output
```bash
NsN1HwFoyN
```
