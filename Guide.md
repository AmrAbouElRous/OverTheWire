# 🚀 Guide: Create a Git Repository and Set Up Auto-Push Script (SSH Version)

This guide explains how to:
- Create a new Git repository locally and on GitHub using **SSH**.
- Push your first commit.
- Set up a script to automatically add, commit, pull (with rebase), and push changes.

---

## 🔧 Step 1: Create a New Git Repository (SSH)

### 1️⃣ Create Local Project Directory

```bash
cd ~/Documents
mkdir ctfs
cd ctfs
```
### 2️⃣ Initialize Git
```bash
git init
```
### 3️⃣ Add an Initial File
```bash
echo "# CTF Notes" > README.md
```
### 4️⃣ Commit the File
```bash
git add .
git commit -m "Initial commit"
```
### 5️⃣ Create GitHub Repository

    Go to github.com

    Create a new repository without initializing with a README

    Copy the SSH URL (looks like: git@github.com:yourusername/ctfs.git)

### 6️⃣ Connect Local Repo to Remote via SSH
```bash
git remote add origin git@github.com:yourusername/ctfs.git
```
### 7️⃣ Push to GitHub
```bash
git branch -M main
git push -u origin main
```
---

## 🤖 Step 2: Create an Auto-Push Script

### 1️⃣ Create the Script File
```bash
nano ~/auto_push.sh
```
### 2️⃣ Paste the Script Below
``` bash
#!/bin/bash

# Set the path to your repo
REPO_PATH="$HOME/Documents/ctfs"
COMMIT_MSG="Auto-update on $(date '+%Y-%m-%d %H:%M:%S')"

# Change to repo directory
cd "$REPO_PATH" || { echo "Repo path not found!"; exit 1; }

# Add all changes
git add .

# Commit with a timestamp
git commit -m "$COMMIT_MSG"

# Pull first to avoid push conflicts
git pull origin main --rebase

# Push to the main branch
git push origin main
```
### 3️⃣ Make the Script Executable

```bash
chmod +x ~/auto_push.sh
```
---

## 🛠️ Troubleshooting: What to Do When Something Goes Wrong

Even with automation, things can go wrong — maybe you committed a broken version or pushed something you didn’t mean to. Don’t worry! Git has your back.

---

### 🔍 View Commit History

You can see your past commits using:

```bash
git log
```
This shows a list of commits with their hashes, authors, dates, and messages.

### ⏪ Go Back to a Previous Version Temporarily

To preview an older version of the repo (read-only state, detached HEAD):


```bash
git checkout <commit-hash>
```

Example:

```bash 
git checkout a1b2c3d4e5f6g7h8i9j0
```

✅ This lets you look at the old version. To return to normal:

```bash
 git checkout main
```
### 🔄 Revert to a Previous Commit (Make It the Latest)
If you want to make a past commit the new current version (and undo all commits after it):
```bash
git reset --hard <commit-hash>
```
⚠️ This will remove all commits after the specified commit from history. Be careful!

### 💡 Pro Tip: Tag Good Versions
Before making major changes, tag a stable version:
```bash
git tag stable-1
```
Then you can return to it anytime:
```bash
git checkout stable-1
```
