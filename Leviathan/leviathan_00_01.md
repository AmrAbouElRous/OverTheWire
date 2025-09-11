# Leviathan Level 0  -> 1

## 🧠 Goal  

Log into Leviathan 0 and find the password for Leviathan 1.  

---

## 🔐 Credentials  

- **Username:** `leviathan0`  
- **Host:** `leviathan.labs.overthewire.org`  
- **Port:** `2223` (SSH)  
- **Password:** `leviathan0`  

---

## 🖥️ Commands Used  

```bash
leviathan0@leviathan:~$ ls -la
total 24
drwxr-xr-x   3 root       root       4096 Aug 15 13:17 .
drwxr-xr-x 150 root       root       4096 Aug 15 13:18 ..
drwxr-x---   2 leviathan1 leviathan0 4096 Aug 15 13:17 .backup
-rw-r--r--   1 root       root        220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root       root       3851 Aug 15 13:09 .bashrc
-rw-r--r--   1 root       root        807 Mar 31  2024 .profile
leviathan0@leviathan:~$ cd .backup
leviathan0@leviathan:~/.backup$ ls
bookmarks.html
leviathan0@leviathan:~/.backup$ cat bookmarks.html | grep "password"
<DT><A HREF="http://leviathan.labs.overthewire.org/passwordus.html | This will be fixed later, the password for leviathan1 is 3QJ3TgzHDq" ADD_DATE="1155384634" LAST_CHARSET="ISO-8859-1" ID="rdf:#$2wIU71">password to leviathan1</A>
leviathan0@leviathan:~/.backup$ 
```
## 📤 Output
```bash
3QJ3TgzHDq
```
