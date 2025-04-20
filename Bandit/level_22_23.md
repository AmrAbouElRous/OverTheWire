# Bandit Level 22 → Level 23

## 🧠 Goal

Level Goal

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
Commands you may need to solve this level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

---

## 🔐 Credentials

- **Username:** `bandit22`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q`

---

## 🖥️ Commands Used

```bash
bandit22@bandit:~$ cd /etc/cron.d/
bandit22@bandit:/etc/cron.d$ ls -l
total 28
-rw-r--r-- 1 root root 123 Apr 10 14:16 clean_tmp
-rw-r--r-- 1 root root 120 Apr 10 14:23 cronjob_bandit22
-rw-r--r-- 1 root root 122 Apr 10 14:23 cronjob_bandit23
-rw-r--r-- 1 root root 120 Apr 10 14:23 cronjob_bandit24
-rw-r--r-- 1 root root 201 Apr  8  2024 e2scrub_all
-rwx------ 1 root root  52 Apr 10 14:24 otw-tmp-dir
-rw-r--r-- 1 root root 396 Jan  9  2024 sysstat
bandit22@bandit:/etc/cron.d$ cat cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
```
whoami will give us bandit22 so we canot get the password for bandit 23 directly
so lets modify it for bandit 23
```bash
bandit22@bandit:/etc/cron.d$ myname=bandit23
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
bandit22@bandit:/etc/cron.d$ echo $mytarget
8ca319486bfbbc3663ea0fbe81326349
cat /tmp/$mytarget
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

```
___

## 💡 Tips
```bash


```
___

## 📤 Output
```bash
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

