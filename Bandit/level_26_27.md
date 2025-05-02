# Bandit Level 26 → Level 27

## 🧠 Goal

Good job getting a shell! Now hurry and grab the password for bandit27!
Commands you may need to solve this level

ls

---

## 🔐 Credentials

- **Username:** `bandit26`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ`

---

## 🖥️ Commands Used
as we know from previous level
bandit26 is not using default /bin/bash instead useing /bin/showtext which also has more inside<br>
so menimize screen when logging then,<br>
type v  	to open vi editor semilar to nano but its terminal based<br>
:set shell=/bin/bash <br>
:sh         OR     :!bash <br>

```bash
bandit26@bandit:~$ ls -l
total 20
-rwsr-x--- 1 bandit27 bandit26 14884 Apr 10 14:23 bandit27-do
-rw-r----- 1 bandit26 bandit26   258 Apr 10 14:23 text.txt
bandit26@bandit:~$ ./bandit27-do
Run a command as another user.
  Example: ./bandit27-do id
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
bandit26@bandit:~$ 
```
___

## 💡 Tips
```bash


```
___

## 📤 Output
```bash
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

