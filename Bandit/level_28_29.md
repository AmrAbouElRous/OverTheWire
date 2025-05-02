# Bandit Level 28 → Level 29

## 🧠 Goal

There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.

Clone the repository and find the password for the next level.
Commands you may need to solve this level

git

---

## 🔐 Credentials

- **Username:** `bandit28`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN`

---

## 🖥️ Commands Used

```bash
bandit28@bandit:~$ ls -l
total 0
bandit28@bandit:~$ mktemp -d tmp/amro.XXX
mktemp: failed to create directory via template ‘tmp/amro.XXX’: No such file or directory
bandit28@bandit:~$ mktemp -d /tmp/amro.XXX
/tmp/amro.ZS5
bandit28@bandit:~$ cd /tmp/amro.ZS5
bandit28@bandit:/tmp/amro.ZS5$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password: 
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/amro.ZS5$ ls -l
total 4
drwxrwxr-x 3 bandit28 bandit28 4096 May  2 17:49 repo
bandit28@bandit:/tmp/amro.ZS5$ cd repo
bandit28@bandit:/tmp/amro.ZS5/repo$ ls -l
total 4
-rw-rw-r-- 1 bandit28 bandit28 111 May  2 17:49 README.md
bandit28@bandit:/tmp/amro.ZS5/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/amro.ZS5/repo$ git log
commit 674690a00a0056ab96048f7317b9ec20c057c06b (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Apr 10 14:23:19 2025 +0000

    fix info leak

commit fb0df1358b1ff146f581651a84bae622353a71c0
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Apr 10 14:23:19 2025 +0000

    add missing data

commit a5fdc97aae2c6f0e6c1e722877a100f24bcaaa46
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Apr 10 14:23:19 2025 +0000

    initial commit of README.md
bandit28@bandit:/tmp/amro.ZS5/repo$ git checkout a5fdc97aae2c6f0e6c1e722877a100f24bcaaa46
Note: switching to 'a5fdc97aae2c6f0e6c1e722877a100f24bcaaa46'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at a5fdc97 initial commit of README.md
bandit28@bandit:/tmp/amro.ZS5/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: <TBD>

bandit28@bandit:/tmp/amro.ZS5/repo$ git checkout fb0df1358b1ff146f581651a84bae622353a71c0
Previous HEAD position was a5fdc97 initial commit of README.md
HEAD is now at fb0df13 add missing data
bandit28@bandit:/tmp/amro.ZS5/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7

bandit28@bandit:/tmp/amro.ZS5/repo$ git checkout master
Previous HEAD position was fb0df13 add missing data
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
bandit28@bandit:/tmp/amro.ZS5/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx
```
___

## 💡 Tips
## 📝 Quick Notes: Git Log & Checkout

### 🔍 `git log`
- Shows the **commit history** of the repository.
- Each commit includes:
  - `commit <hash>` — the unique ID of the commit.
  - Author name and date.
  - Commit message.

**Usage:**
```bash
git log
```
Sample Output:

commit a1b2c3d4e5f6g7h8i9j0
Author: Some User <user@example.com>
Date:   Fri May 2 17:45:00 2025 +0000

    Updated README with placeholder

🔁 git checkout <commit-hash>

    Switches to a specific commit (detached HEAD state).

    Useful for viewing older versions of the project.

Usage:
```bash
git checkout a1b2c3d
cat README.md
```
🔄 Return to the latest commit

To go back to the latest version on the main branch:

```bash
git checkout main
```
or, if the main branch is named master:
```bash
git checkout master
```
___

## 📤 Output
```bash
4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```

