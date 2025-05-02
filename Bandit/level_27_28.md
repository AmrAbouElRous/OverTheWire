# Bandit Level 27 → Level 28

## 🧠 Goal

There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.

Clone the repository and find the password for the next level.
Commands you may need to solve this level

git

---

## 🔐 Credentials

- **Username:** `bandit27`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB`

---

## 🖥️ Commands Used

```bash
bandit27@bandit:~$ mktemp -d /tmp/amro.XXX
/tmp/amro.ZHH
bandit27@bandit:~$ cd /tmp/amro.ZHH
bandit27@bandit:/tmp/amro.ZHH$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password: 
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/amro.ZHH$ ls
repo
bandit27@bandit:/tmp/amro.ZHH$ cd repo
bandit27@bandit:/tmp/amro.ZHH/repo$ ls
README
bandit27@bandit:/tmp/amro.ZHH/repo$ cat README
The password to the next level is: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
#
```
___

## 💡 Tips
```bash
# Syntax to clone is host:portnumber
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo

```
___

## 📤 Output
```bash
Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```

