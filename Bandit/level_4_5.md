# Bandit Level 4 → Level 5

## 🧠 Goal

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

---

## 🔐 Credentials

- **Username:** `bandit4`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ `

---

## 🖥️ Commands Used

```bash
# Connection
ssh bandit4@bandit.labs.overthewire.org -p 2220

bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09

# to open a file that starts with a dash put ./ before the name
bandit4@bandit:~/inhere$ cat ./-file00
�ŉOT���S �plS]-EH�t�:-�Z�
# go throug all of them until u gain a human-readable text
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$ 


```
## 📤 Output
```bash
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

