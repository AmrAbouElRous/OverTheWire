# Bandit Level 14 → Level 15

## 🧠 Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

---

## 🔐 Credentials

- **Username:** `bandit14`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`

---

## 🖥️ Commands Used

```bash
bandit14@bandit:~$ echo MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS | nc localhost 30000
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo


#
```
___

## 💡 Tips
```bash
echo MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS | nc localhost 30000

This opens a TCP connection to port 3000 on localhost.

```
___

## 📤 Output
```bash
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

