# Leviathan Level 0  

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
# connect to leviathan0
ssh leviathan0@leviathan.labs.overthewire.org -p 2223

# list home directory
ls -la

# read the password file
cat .pass
