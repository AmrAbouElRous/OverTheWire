# Bandit Level 32 → Level 33

## 🧠 Goal

After all this git stuff, it’s time for another escape. Good luck!
Commands you may need to solve this level

sh, man

---

## 🔐 Credentials

- **Username:** `bandit32`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K`

---

## 🖥️ Commands Used

```bash
┌──(amro㉿amro)-[~]
└─$ ssh bandit32@bandit.labs.overthewire.org -p 2220 /bin/bash
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit32@bandit.labs.overthewire.org's password: 
WELCOME TO THE UPPERCASE SHELL
>> ls
>> sh: 1: LS: Permission denied
$0
cd /etc/bandit_pass 
ls
bandit0
bandit1
bandit10
bandit11
bandit12
bandit13
bandit14
bandit15
bandit16
bandit17
bandit18
bandit19
bandit2
bandit20
bandit21
bandit22
bandit23
bandit24
bandit25
bandit26
bandit27
bandit28
bandit29
bandit3
bandit30
bandit31
bandit32
bandit33
bandit4
bandit5
bandit6
bandit7
bandit8
bandit9
cat bandit33
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
#BONUS
printenv
USER=bandit32
SSH_CLIENT=156.198.250.230 13618 2220
XDG_SESSION_TYPE=tty
HOME=/home/bandit32
OLDPWD=/home/bandit32
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/11032/bus
LOGNAME=bandit32
XDG_SESSION_CLASS=user
XDG_SESSION_ID=137610
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
XDG_RUNTIME_DIR=/run/user/11032
LANG=C.UTF-8
SHELL=/home/bandit32/uppershell
PWD=/etc/bandit_pass
SSH_CONNECTION=156.198.250.230 13618 10.0.1.228 2220
```
___

## 💡 Tips

Linux has Variables called local variables (valid in current shell), shell variables (set up by shell) and environment variables (valid systemwide). These variables have their names in uppercase only. They are defined by writing VAR_NAME=var_value in the command line. To see the content of a variable, you can write echo $VAR_NAME.

To print all environment variables, you can use printenv.

Some common that are good to know are:

    TERM -  current terminal emulation
    HOME - the path to home directory of currently logged in user
    LANG - current locales settings
    PATH - directory list to be searched when executing commands
    PWD - pathname of the current working directory
    SHELL/0 - the path of the current user’s shell
    USER - currently logged-in user

---
So everything we type seems to be made uppercase. The commands we have used so far however, are all lower-case and do not work. The one thing in Linux that is uppercase is variables. Specifically, the variable $0 has a reference to a shell. You can see this with echo $0 on your machine
---
$0 in shell scripting refers to:

    The name of the current shell or script being executed.

In an interactive shell:

    $0 usually holds the path to the shell binary (e.g., /bin/bash, /bin/sh).

    Running $0 (as a command) tries to invoke that shell again — which might drop you into a fresh shell outside the restricted environment.

___

## 📤 Output
```bash
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```

