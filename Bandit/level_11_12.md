# Bandit Level 11 → Level 12

## 🧠 Goal

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

---

## 🔐 Credentials

- **Username:** `bandit11`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`

---

## 🖥️ Commands Used

```bash
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
bandit11@bandit:~$ tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
#
```
___

## 💡 Tips
```bash
Original:  A B C D E F G H I J K L M N O P Q R S T U V W X Y Z  
Shifted :  N O P Q R S T U V W X Y Z A B C D E F G H I J K L M

tr 'A-Za-z' 'N-ZA-Mn-za-m'

🧠 So what does 'A-Za-z' mean?

It defines a character set:

    A-Z = all uppercase letters

    a-z = all lowercase letters

So 'A-Za-z' means: all letters, both uppercase and lowercase.
🔁 What about 'N-ZA-Mn-za-m'?

This is the ROT13-rotated version of the alphabet:

    N-ZA-M → Rotates uppercase letters:

        N through Z (first half)

        A throug M (second half)

    n-za-m → Rotates lowercase letters the same way:

        n through z (first half)

        a throug m (second half)

So this maps every letter 13 places forward in the alphabet, looping around when needed.

```
___

## 📤 Output
```bash
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

