# Bandit Level 13 → Level 14

## 🧠 Goal
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

---

## 🔐 Credentials

- **Username:** `bandit13`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`

---

## 🖥️ Commands Used

```bash
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```
___

## 💡 Tips

### 🔐 What is SSH?

SSH (Secure Shell) is a protocol that lets you securely connect to another machine (typically a remote server) over a network.

It encrypts all data between your machine and the remote machine, so it’s safe from eavesdropping

### 🔐 Public Key Authentication (used here)

SSH normally uses passwords, but for extra security or automation, it can use key pairs:

    Public key: Goes on the server (~/.ssh/authorized_keys).

    Private key: Stays on your machine (or in this case, provided by Bandit as sshkey.private).

When you connect:

    The client (you) presents the private key.

    The server checks if it matches the authorized public key.

    If it matches → you're allowed in!

No password is needed.

### 🔐 Why is this more secure than passwords?

    Passwords can be guessed, brute-forced, or stolen.

    Private keys are long and random, nearly impossible to guess.

    They never travel over the network.

    You can add a passphrase to the private key for extra protection

```bash
# if you already in there machine you can do any of them
ssh -i sshkey.private bandit14@localhost -p 2220
# or
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

#-i sshkey.private	Specifies the private key file used for authentication instead of a password.

```
___

## 📤 Output
```bash
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS 
```

