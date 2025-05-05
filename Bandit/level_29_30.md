# Bandit Level 29 → Level 30

## 🧠 Goal

There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.

Clone the repository and find the password for the next level.
Commands you may need to solve this level

git

---

## 🔐 Credentials

- **Username:** `bandit29`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7`

---

## 🖥️ Commands Used

```bash
bandit29@bandit:~$ mktemp -d /tmp/amro.XXX
/tmp/amro.34P
bandit29@bandit:~$ cd /tmp/amro.34P
bandit29@bandit:/tmp/amro.34P$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password: 
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), 1.44 KiB | 736.00 KiB/s, done.
Resolving deltas: 100% (2/2), done.

bandit29@bandit:/tmp/amro.34P$ ls -l
total 4
drwxrwxr-x 3 bandit29 bandit29 4096 May  5 18:02 repo
bandit29@bandit:/tmp/amro.34P$ cd repo
bandit29@bandit:/tmp/amro.34P/repo$ ls -l
total 4
-rw-rw-r-- 1 bandit29 bandit29 131 May  5 18:02 README.md
bandit29@bandit:/tmp/amro.34P/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/amro.34P/repo$ git log --all --graph
* commit a97d0dbf8fd910ead6fcf648829ff55c1a629c8e (origin/dev)
| Author: Morla Porla <morla@overthewire.org>
| Date:   Thu Apr 10 14:23:21 2025 +0000
| 
|     add data needed for development
| 
* commit 3910630172946c9ffb75842922e394b772c672bd
| Author: Ben Dover <noone@overthewire.org>
| Date:   Thu Apr 10 14:23:21 2025 +0000
| 
|     add gif2ascii
|   
| * commit c2e20a2bcc4815a984fbef4c7a96ca6e4de35c48 (origin/sploits-dev)
|/  Author: Morla Porla <morla@overthewire.org>
|   Date:   Thu Apr 10 14:23:21 2025 +0000
|   
|       add some silly exploit, just for shit and giggles
| 
* commit 3b8b91fc3c48f1a19d05670fd45d3e3f2621fcfa (HEAD -> master, origin/master, origin/HEAD)
| Author: Ben Dover <noone@overthewire.org>
| Date:   Thu Apr 10 14:23:21 2025 +0000
| 
|     fix username
| 
* commit 8d2ffeb5e45f87d0abb028aa796e3ebb63c5579c
  Author: Ben Dover <noone@overthewire.org>
  Date:   Thu Apr 10 14:23:21 2025 +0000
  
      initial commit of README.md
#
```
or use
```bash
bandit29@bandit:/tmp/amro.34P/repo$ git branch -a
* (HEAD detached at 3b8b91f)
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/amro.34P/repo$ git checkout remotes/origin/dev
Previous HEAD position was 3b8b91f fix username
HEAD is now at a97d0db add data needed for development
bandit29@bandit:/tmp/amro.34P/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```
___

## 💡 Tips
```bash
The basic commands for working with branches are:

    git branch: List (-a), create, or delete branches
    git checkout <branch_name>/git switch <branch_name>: Switch branches
    git merge: Join two or more branches

I found using "git log --all --graph" is easier for me. It will list out all branches you have in graph representation on the terminal.
```
___

## 📤 Output
```bash
qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```

