# Bandit Level 30 → Level 31

## 🧠 Goal

There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

Clone the repository and find the password for the next level.
Commands you may need to solve this level

git

---

## 🔐 Credentials

- **Username:** `bandit30`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL`

---

## 🖥️ Commands Used

```bash
bandit30@bandit:~$ mktemp -d /tmp/amro.XXX
/tmp/amro.Afy
bandit30@bandit:~$ cd /tmp/amro.Afy
bandit30@bandit:/tmp/amro.Afy$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password: 
Permission denied, please try again.
bandit30-git@localhost's password: 
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/amro.Afy$ ls -l
total 4
drwxrwxr-x 3 bandit30 bandit30 4096 May  6 17:55 repo
bandit30@bandit:/tmp/amro.Afy$ cd repo
bandit30@bandit:/tmp/amro.Afy/repo$ ls -l
total 4
-rw-rw-r-- 1 bandit30 bandit30 30 May  6 17:55 README.md
bandit30@bandit:/tmp/amro.Afy/repo$ git log --all --graph
* commit fb05775f973256dc6d8d5bb6a8e6b96b0d8795c8 (HEAD -> master, origin/master, origin/HEAD)
  Author: Ben Dover <noone@overthewire.org>
  Date:   Thu Apr 10 14:23:24 2025 +0000
  
      initial commit of README.md
bandit30@bandit:/tmp/amro.Afy/repo$ git checkout fb05775f973256dc6d8d5bb6a8e6b96b0d8795c8
Note: switching to 'fb05775f973256dc6d8d5bb6a8e6b96b0d8795c8'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at fb05775 initial commit of README.md
bandit30@bandit:/tmp/amro.Afy/repo$ ls
README.md
bandit30@bandit:/tmp/amro.Afy/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/amro.Afy/repo$ git tag
secret
bandit30@bandit:/tmp/amro.Afy/repo$ git show secret
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
#
```
___

## 💡 Tips

Git tagging is a way to mark specific points in the history of the repository. One example would be to mark release points of the software. The command to see the tags is `git tag`. To create a tag the command is `git tag -a <tag_name> -m <"tag description/message">.` To see more details, like the tag message and commit, you can use the following command: `git show <tag_name>`.

___

## 📤 Output
```bash
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```


