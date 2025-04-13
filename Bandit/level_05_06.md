# Bandit Level 5 → Level 6

## 🧠 Goal

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable


---

## 🔐 Credentials

- **Username:** `bandit5`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`

---

## 🖥️ Commands Used

```bash
# connection
ssh bandit5@bandit.labs.overthewire.org -p 2220

bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17

# find all files in the directory that`s human readable with size 1033 bytes and not executable
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
./maybehere07/.file2
#open the file
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
                                   
#
```
## 📤 Output
```bash
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

