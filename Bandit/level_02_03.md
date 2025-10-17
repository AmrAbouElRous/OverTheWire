# Bandit Level 2->3

**Goal:** The password for the next level is stored in a file called spaces in this filename located in the home directory

---

## 🧠 Goal

The password for the next level is stored in a file called spaces in this filename located in the home directory

---

## 🔐 Credentials

- **Username:** `bandit2`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

---

## 🖥️ Commands Used

```bash
# Connect to the server using SSH
ssh bandit2@bandit.labs.overthewire.org -p 2220


# Show all files in the directory
bandit2@bandit:~$ ls
spaces in this filename


#Show the content of a file with space in its name
bandit2@bandit:~$ cat ./"--spaces in this filename--"
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

#or

bandit2@bandit:~$ cat ./--spaces\ in\ this\ filename-- 
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx


#
```
## 📤 Output
```bash
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```
## 💡 Tips
✅ Option 3: Use tab completion

Type:

cat ./--

then press Tab — the shell will fill in the rest safely for you
