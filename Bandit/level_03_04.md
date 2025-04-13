# Bandit Level 3 → Level 4

## 🧠 Goal

The password for the next level is stored in a hidden file in the inhere directory.

---

## 🔐 Credentials

- **Username:** `bandit3`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

---

## 🖥️ Commands Used

```bash
# Connection
ssh bandit3@bandit.labs.overthewire.org -p 2220

bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
# Show all including hidden 
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ


```
## 📤 Output
```bash
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ 
```

