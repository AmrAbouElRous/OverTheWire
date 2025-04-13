# Bandit Level 9 → Level 10

## 🧠 Goal

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

---

## 🔐 Credentials

- **Username:** `bandit9`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

---

## 🖥️ Commands Used

```bash
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep -E '^=+'
========== the
========== password{k
=========== is
=wDk
=3?lOt
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
=D!f


#
```
___

## 💡 Tips
```bash
# 🧱 Basic Regex Building Blocks

| Pattern      | Meaning                              | Example Match       |
|--------------|--------------------------------------|---------------------|
| `.`          | Any **one character** except newline  | `c.t` → `cat`, `cut` |
| `*`          | 0 or more of the previous character  | `go*` → `g`, `gooo` |
| `+`          | 1 or more of the previous character  | `go+` → `go`, `gooo` |
| `?`          | 0 or 1 of the previous character     | `colou?r` → `color`, `colour` |
| `^`          | Start of a line                      | `^pass` → `password` |
| `$`          | End of a line                        | `word$` → `password` |
| `[]`         | Any one character in the set         | `[aeiou]` → any vowel |
| `[^]`        | Not in the set                       | `[^0-9]` → not a digit |
| `{n}`        | Exactly `n` repeats                  | `a{3}` → `aaa` |
| `{n,}`       | `n` or more repeats                  | `a{2,}` → `aa`, `aaa` |
| `{n,m}`      | Between `n` and `m` repeats          | `a{2,4}` → `aa`, `aaa`, `aaaa` |
| `|`          | OR                                   | `cat|dog` → `cat` or `dog` |
| `()`         | Grouping                             | `(ha)+` → `ha`, `hahaha` |

---

## 🧠 Useful Regex Examples

| Goal                              | Regex                      |
|-----------------------------------|----------------------------|
| Match a password like `====abc123`| `^=+[^=]+`                 |
| Match a 5-digit zip code          | `\b\d{5}\b`                |
| Match an email address            | `[a-zA-Z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}` |
| Match a date `dd/mm/yyyy`         | `\b\d{2}/\d{2}/\d{4}\b`    |
| Match lines containing numbers    | `.*[0-9].*`                |

> 💡 In the shell, always **quote** regex patterns to avoid shell expansion: `'^[A-Z]+$'`

---

## 🧰 Tools That Use Regex

- `grep`, `sed`, `awk` (command line)
- `find` / `locate`
- `Python`, `JavaScript`, `Perl`, etc.
- Text editors: VS Code, Sublime Text, Notepad++


```
___

## 📤 Output
```bash
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

