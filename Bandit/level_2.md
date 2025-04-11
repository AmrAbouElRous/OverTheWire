# Bandit Level 2

**Goal:** The password for the next level is stored in a file called - located in the home directory

---

## 🧠 Goal

The password for the next level is stored in a file called - located in the home directory

---

## 🔐 Credentials

- **Username:** `bandit1`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

---

## 🖥️ Commands Used

```bash
# Connect to the server using SSH
ssh bandit1@bandit.labs.overthewire.org -p 2220

# Print working directory
bandit1@bandit:~$ pwd
/home/bandit1

# Show all files in the directory
bandit1@bandit:~$ ls
-

#Show the content of a dash named file
bandit1@bandit:~$ cat < -

#
```
## 📤 Output
```bash
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

