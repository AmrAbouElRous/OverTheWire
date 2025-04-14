# Bandit Level 12 → Level 13

## 🧠 Goal

The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

---

## 🔐 Credentials

- **Username:** `bandit12`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`

---

## 🖥️ Commands Used

```bash
# comments
ssh bandit0@bandit.labs.overthewire.org -p 2220

#
```
___

## 💡 Tips

# Continue this loop:

| **File Output**   | **What to Do**                                          |
|-------------------|---------------------------------------------------------|
| **gzip**          | `mv test test.gz && gunzip test.gz`                     |
| **bzip2**         | `mv test test.bz2 && bunzip2 test.bz2`                  |
| **tar archive**   | `tar -xf test` (no renaming needed)                     |
| **ASCII text**    | `cat test` and find the password inside                 |

# Commands you may need to solve this level

tar, gzip, bzip2, xxd, mkdir, cp, mv, file
___

## 📤 Output
```bash
password gained level 1 
```

