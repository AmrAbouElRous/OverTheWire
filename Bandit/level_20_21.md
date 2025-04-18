# Bandit Level 20 → Level 21

## 🧠 Goal

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think
Commands you may need to solve this level

ssh, nc, cat, bash, screen, tmux, Unix ‘job control’ (bg, fg, jobs, &, CTRL-Z, …)

---

## 🔐 Credentials

- **Username:** `bandit20`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`

---

## 🖥️ Commands Used

```bash
# comments
ssh bandit0@bandit.labs.overthewire.org -p 2220

#
```
___

## 💡 Tips
```bash


```
___

## 📤 Output
```bash
password gained level 1
```

