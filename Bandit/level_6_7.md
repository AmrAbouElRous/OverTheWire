# Bandit Level 6 → Level 7

## 🧠 Goal

The password for the next level is stored somewhere on the server and has all of the following properties:
    owned by user bandit7
    owned by group bandit6
    33 bytes in size

---

## 🔐 Credentials

- **Username:** `bandit6`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

---

## 🖥️ Commands Used

```bash
bandit6@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  .profile
# find from root and remove eror message like premission denied
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

#
```
## 💡 Tips
```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

# /	serach from root
# 2> 	redirect standard eror
# /dev/null 	blackhole file anything goes here disappers

```

## 📤 Output
```bash
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

