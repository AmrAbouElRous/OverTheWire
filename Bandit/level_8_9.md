# Bandit Level 8 → Level 9

## 🧠 Goal

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

---

## 🔐 Credentials

- **Username:** `bandit8`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`

---

## 🖥️ Commands Used

```bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
bandit8@bandit:~$ sort data.txt | uniq -u | wc -l
1

#
```
___

## 💡 Tips
```bash
The sort command is like cat in that it displays the contents of the file however it sorts the file lexicographically by lines (it reorders them alphabetically so that matching ones are together).

The | is a pipe that redirects the output from one command into another.

The uniq command reports or omits repeated lines and by passing it the -u argument we tell it to report only unique lines.

Used together like this, the command will sort data.txt lexicographically by each line, find the unique line and print it back in the terminal for you.

```
___

## 📤 Output
```bash
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM 
```

