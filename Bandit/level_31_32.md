# Bandit Level 31 → Level 32

## 🧠 Goal

There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.

Clone the repository and find the password for the next level.
Commands you may need to solve this level

git

---

## 🔐 Credentials

- **Username:** `bandit31`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy`

---

## 🖥️ Commands Used

```bash
andit31@bandit:~$ mktemp -d tmp/amro.XXX
mktemp: failed to create directory via template ‘tmp/amro.XXX’: No such file or directory
bandit31@bandit:~$ mktemp -d /tmp/amro.XXX
/tmp/amro.Ep1
bandit31@bandit:~$ cd /tmp/amro.Ep1
bandit31@bandit:/tmp/amro.Ep1$ ls -la
total 588
drwx------    2 bandit31 bandit31   4096 May  6 19:05 .
drwxrwx-wt 4030 root     root     593920 May  6 19:06 ..
bandit31@bandit:/tmp/amro.Ep1$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), 382 bytes | 382.00 KiB/s, done.
bandit31@bandit:/tmp/amro.Ep1$ ls -la
total 592
drwx------    3 bandit31 bandit31   4096 May  6 19:06 .
drwxrwx-wt 4031 root     root     593920 May  6 19:06 ..
drwxrwxr-x    3 bandit31 bandit31   4096 May  6 19:06 repo
bandit31@bandit:/tmp/amro.Ep1$ cd repo
bandit31@bandit:/tmp/amro.Ep1/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 May  6 19:06 .
drwx------ 3 bandit31 bandit31 4096 May  6 19:06 ..
drwxrwxr-x 8 bandit31 bandit31 4096 May  6 19:06 .git
-rw-rw-r-- 1 bandit31 bandit31    6 May  6 19:06 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 May  6 19:06 README.md
bandit31@bandit:/tmp/amro.Ep1/repo$ cat .gitignore
*.txt
# i was experiting what if i delted .gitignore and it worked
bandit31@bandit:/tmp/amro.Ep1/repo$ rm .gitignore
bandit31@bandit:/tmp/amro.Ep1/repo$ ls -la
total 16
drwxrwxr-x 3 bandit31 bandit31 4096 May  6 19:07 .
drwx------ 3 bandit31 bandit31 4096 May  6 19:06 ..
drwxrwxr-x 8 bandit31 bandit31 4096 May  6 19:06 .git
-rw-rw-r-- 1 bandit31 bandit31  147 May  6 19:06 README.md
bandit31@bandit:/tmp/amro.Ep1/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
bandit31@bandit:/tmp/amro.Ep1/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/amro.Ep1/repo$ cat key.txt
May I come in?
bandit31@bandit:/tmp/amro.Ep1/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 May  6 19:09 .
drwx------ 3 bandit31 bandit31 4096 May  6 19:06 ..
drwxrwxr-x 8 bandit31 bandit31 4096 May  6 19:06 .git
-rw-rw-r-- 1 bandit31 bandit31   15 May  6 19:09 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 May  6 19:06 README.md
bandit31@bandit:/tmp/amro.Ep1/repo$ file key.txt
key.txt: ASCII text
bandit31@bandit:/tmp/amro.Ep1/repo$ git init
Reinitialized existing Git repository in /tmp/amro.Ep1/repo/.git/
bandit31@bandit:/tmp/amro.Ep1/repo$ git add .
bandit31@bandit:/tmp/amro.Ep1/repo$ git commit -m "huh i deleted .gitignore haha"
[master 4160e46] huh i deleted .gitignore haha
 2 files changed, 1 insertion(+), 1 deletion(-)
 delete mode 100644 .gitignore
 create mode 100644 key.txt
 bandit31@bandit:/tmp/amro.Ep1/repo$ git push -u origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 299 bytes | 299.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'

```
#### Bonus to see the difference between that 2 commits

```bash
bandit31@bandit:/tmp/amro.Ep1/repo$ git log                                                          
commit 4160e465bdaab7feab7d410c55ce5cc0fc6bc46a (HEAD -> master)
Author: bandit31 <bandit31@overthewire.org>
Date:   Tue May 6 19:11:05 2025 +0000

    huh i deleted .gitignore haha

commit 9f2814daa679b29d2c8f78f2766e7e9332445a41 (origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Apr 10 14:23:26 2025 +0000

    initial commit
bandit31@bandit:/tmp/amro.Ep1/repo$ git checkout 9f2814daa679b29d2c8f78f2766e7e9332445a41
Note: switching to '9f2814daa679b29d2c8f78f2766e7e9332445a41'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 9f2814d initial commit
bandit31@bandit:/tmp/amro.Ep1/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 May  6 19:12 .
drwx------ 3 bandit31 bandit31 4096 May  6 19:06 ..
drwxrwxr-x 8 bandit31 bandit31 4096 May  6 19:12 .git
-rw-rw-r-- 1 bandit31 bandit31    6 May  6 19:12 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 May  6 19:06 README.md
bandit31@bandit:/tmp/amro.Ep1/repo$ git checkout 4160e465bdaab7feab7d410c55ce5cc0fc6bc46a
Previous HEAD position was 9f2814d initial commit
HEAD is now at 4160e46 huh i deleted .gitignore haha
bandit31@bandit:/tmp/amro.Ep1/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 May  6 19:13 .
drwx------ 3 bandit31 bandit31 4096 May  6 19:06 ..
drwxrwxr-x 8 bandit31 bandit31 4096 May  6 19:13 .git
-rw-rw-r-- 1 bandit31 bandit31   15 May  6 19:13 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 May  6 19:06 README.md

```
___

## 💡 Tips
A little bit of Theory

The introduction to Git can be found in Level 28 and Level 29.

Git Commit saves the currently made changes with a message describing these changes. The flag -a makes sure all modified/deleted files are staged but it should be tracked first.
✅ git commit -a auto-stages:

    Changes to already tracked files (files you previously added with git add).

    That includes modifications and deletions.

❌ git commit -a does NOT auto-stage:

    Brand new files (untracked files — ones Git has never seen before).

✔ Final Answer:

    Using git add . with git commit -m is more comprehensive than git commit -a -m, because it includes new files too.

Git Push updates local changes in remote repositories. When pushing for the first time, you should also define the branch with -u.
✅ Summary:

| Command                       | Use case                               |
| ----------------------------- | -------------------------------------- |
| `git push -u origin <branch>` | First time pushing that branch         |
| `git push`                    | After upstream is set (thanks to `-u`) |


Git Ignore is a file with the filename ‘.gitignore’. In this file, all file names/extensions that should be ignored by the commit are written. This means if a file which is in the ignore file is created/changed, it will not be part of the commit/repository. Git ignore also allows for wildcards. (For example, : ‘*.pyc’ means all files with the ending ‘.pyc’ will be ignored.) There are pre-written files for specific situations and languages, like this one for Python.

Git Add updates what files will be part of the next commit. The -f flag forces files to be able to be committed, even when they are normally ignored.

✅ git add .

    What it does: Stages all changes in the current directory and subdirectories, including:

        Modified tracked files

        Deleted tracked files

        New untracked files (except ignored ones)

    Won't include: Files listed in .gitignore (ignored files)

✅ git add -f <file_name>

    -f means force.

    What it does: Stages a file even if it's ignored (i.e., listed in .gitignore).
    
✅ Summary:

| Command             | Purpose                                 |
| ------------------- | --------------------------------------- |
| `git add .`         | Adds all changes (except ignored files) |
| `git add -f <file>` | Adds even ignored files (forced)        |


✅ If you delete .gitignore, then:

    Git will no longer ignore the files listed in it.

    So, previously ignored files (like .env, node_modules/, etc.) will now be seen as untracked files.

    That means you can add them with git add or git add . normally, without needing -f.
___

## 📤 Output
```bash
3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```

