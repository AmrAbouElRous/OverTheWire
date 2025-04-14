# Bandit Level 0->1

## 🧠 Goal

put your goal here

---

## 🔐 Credentials

- **Username:** `bandit0`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `password gained from the previous level level 0`

---

## 🖥️ Commands Used

```bash
# comments
ssh bandit0@bandit.labs.overthewire.org -p 2220

#
```
___

## 💡 Tips
```bash
# Continue this loop:

| **File Output**   | **What to Do**                                          |
|-------------------|---------------------------------------------------------|
| **gzip**          | `mv test test.gz && gunzip test.gz`                     |
| **bzip2**         | `mv test test.bz2 && bunzip2 test.bz2`                  |
| **tar archive**   | `tar -xf test` (no renaming needed)                     |
| **ASCII text**    | `cat test` and find the password inside                 |


```
___

## 📤 Output
```bash
password gained level 1 
```

