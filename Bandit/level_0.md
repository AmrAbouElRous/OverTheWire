# Bandit Level 0

**Goal:** SSH into the server and find the password.

```bash
# Command to connect
ssh bandit0@bandit.labs.overthewire.org -p 2220

# After login, to find the password
cat readme


# Bandit Level 0 Walkthrough

## 🧠 Goal
The goal of this level is to log into the game using SSH and read the contents of a file called `readme`.

---

## 🔐 Credentials
- **Username:** `bandit0`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`

---

## 🖥️ Commands Used

```bash
# Connect to the server using SSH
ssh bandit0@bandit.labs.overthewire.org -p 2220

# Once logged in, list files
ls

# Read the content of the 'readme' file
cat readme

## Output
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
