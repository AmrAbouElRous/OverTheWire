# Bandit Level 19 → Level 20

## 🧠 Goal

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

#### Helpful Reading Material

setuid on Wikipedia


---

## 🔐 Credentials

- **Username:** `bandit19`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8`

---

## 🖥️ Commands Used

```bash
bandit19@bandit:~$ ls -l
total 16
-rwsr-x--- 1 bandit20 bandit19 14884 Apr 10 14:23 bandit20-do
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
bandit19@bandit:~$ ./bandit20-do ls /etc/bandit_pass
bandit0   bandit12  bandit16  bandit2   bandit23  bandit27  bandit30  bandit4  bandit8
bandit1   bandit13  bandit17  bandit20  bandit24  bandit28  bandit31  bandit5  bandit9
bandit10  bandit14  bandit18  bandit21  bandit25  bandit29  bandit32  bandit6
bandit11  bandit15  bandit19  bandit22  bandit26  bandit3   bandit33  bandit7


#
```
___

## 💡 Tips
```bash
bandit19@bandit:~$ ls -l
total 16
-rwsr-x--- 1 bandit20 bandit19 14884 Apr 10 14:23 bandit20-do
```
🧩 Step-by-step breakdown of -rwsr-x---

Here it is again, broken into 4 parts:

1  2 3 4
- r w s r - x - - -

1️⃣ First character: -

This tells you what kind of thing this is.

    - = regular file

    d = directory

    l = symbolic link

✅ In our case, it's a regular file.
2️⃣ Next three: r w s

This shows permissions for the owner of the file (which is bandit20):

    r → read permission ✅

    w → write permission ✅

    s → this is the special part — it replaces the normal x (execute) and means setuid

    ⚠️ Setuid means: If anyone runs this file, it runs as the file's owner (bandit20), not as the person running it (you = bandit19)

Normally you'd expect rwx, but because of the setuid bit, it's shown as rws.
3️⃣ Next three: r - x

This is for the group (which is bandit19):

    r → read permission ✅

    - → no write permission ❌

    x → execute permission ✅

This means: if you're in the bandit19 group (which you are), you can read and run the file, but not edit it.
4️⃣ Last three: - - -

This is for others (everyone else on the system):

    No permissions at all.

✅ What does all of this mean?

Let’s summarize:

    The file is a normal file

    It is owned by bandit20

    It has the setuid bit, so:

        When you run this file, it runs as bandit20 (not bandit19)

    You (bandit19) are allowed to run the file

So it's a special tool that lets you temporarily act as bandit20 — just for running a command.
___

## 📤 Output
```bash
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

