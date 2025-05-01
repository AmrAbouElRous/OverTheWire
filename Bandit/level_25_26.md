# Bandit Level 25 → Level 26

## 🧠 Goal

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

    NOTE: if you’re a Windows user and typically use Powershell to ssh into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.

Commands you may need to solve this level

ssh, cat, more, vi, ls, id, pwd

---

## 🔐 Credentials

- **Username:** `bandit25`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `iCi86ttT4KSNe1armKiwbQNmB3YJP3q4`

---

## 🖥️ Commands Used

```bash
bandit25@bandit:~$ ls -l 
total 4
-r-------- 1 bandit25 bandit25 1679 Apr 10 14:23 bandit26.sshkey
bandit25@bandit:~$ file bandit26.sshkey
bandit26.sshkey: PEM RSA private key

bandit25@bandit:~$ cat /etc/passwd | grep "bandit26"
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
#bandit25:x:11025:11025:bandit level 25:/home/bandit25:/bin/bash
#bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
#bandit27:x:11027:11027:bandit level 27:/home/bandit27:/bin/bash

bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
```
since it doesnot use the default /bin/bash instead using showtext with more
so connect using the private key and scale window to small so that "more" command work <br>
type v <br>
:set shell=/bin/bash <br>
:sh

```bash
bandit26@bandit:~$ cat /etc/bandit_pass/bandit26
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```
___

## 💡 Tips
/etc :is present in evey linux-unix system it is a standard directory dfined by default system hireachy FSH
/etc/passwd : common for every linux=unix system ,it is a textfile that stores information about all users accounts on the system

since "more" command work on large text so the trick is to minimzie our window so "more" work and donot lose our connection
then type v to enter vi/vim editor
:set shell=/bin/bash
:sh 

note :sh  is similar to :!bash       which give you subshell
You get a live shell session
#### what is vi ? 

vi is a text editor for Unix and Linux systems. It stands for "Visual Editor" and is one of the oldest and most commonly available editors on Unix-like systems.
🧰 Key Features of vi:

    It's terminal-based (runs in the command line).

    Very lightweight and fast.

    Available on almost every Unix/Linux machine.

    Has two main modes:

        Normal mode (navigation, commands)

        Insert mode (typing/editing text)

🕹️ Basic vi Commands:
Action	Command
Enter insert mode	Press i
Exit insert mode	Press Esc
Save file	:w then Enter
Quit vi	:q then Enter
Save and quit	:wq or ZZ
Quit without saving	:q!
Delete a line	dd (in normal mode)
Move cursor	h (left), j (down), k (up), l (right)
🧠 Tip:

If you're new to vi, you might prefer nano at first, but learning basic vi is useful because it's always installed, even on minimal systems.

[More Command in Linux – GeeksforGeeks](https://www.geeksforgeeks.org/more-command-in-linux-with-examples/)

[Vi Editor in Unix – GeeksforGeeks](https://www.geeksforgeeks.org/vi-editor-unix/)

___

## 📤 Output
```bash
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```

