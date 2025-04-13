# Bandit Level 10 → Level 11

## 🧠 Goal

The password for the next level is stored in the file data.txt, which contains base64 encoded data

---

## 🔐 Credentials

- **Username:** `bandit10`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`

---

## 🖥️ Commands Used
```bash
bandit10@bandit:~$ls
data.txt
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

```
___

## 💡 Tips
```bash
base64
base64 -d

```
___

## 📤 Output
```bash
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

