# Bandit Level 21 → Level 22

## 🧠 Goal

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

Commands you may need to solve this level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

---

## 🔐 Credentials

- **Username:** `bandit21`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `EeoULMCra2q0dSkYj561DX7s1CpBuOBt`

---

## 🖥️ Commands Used

```bash
bandit21@bandit:~$ cd /etc/cron.d
bandit21@bandit:/etc/cron.d$ ls -l
total 28
-rw-r--r-- 1 root root 123 Apr 10 14:16 clean_tmp
-rw-r--r-- 1 root root 120 Apr 10 14:23 cronjob_bandit22
-rw-r--r-- 1 root root 122 Apr 10 14:23 cronjob_bandit23
-rw-r--r-- 1 root root 120 Apr 10 14:23 cronjob_bandit24
-rw-r--r-- 1 root root 201 Apr  8  2024 e2scrub_all
-rwx------ 1 root root  52 Apr 10 14:24 otw-tmp-dir
-rw-r--r-- 1 root root 396 Jan  9  2024 sysstat
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

```
___

## 💡 Tips
```bash


```
___

## 📤 Output
```bash
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

