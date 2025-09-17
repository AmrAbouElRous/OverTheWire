# Leviathan Level 4->5  

## 🧠 Goal  

Log into Leviathan 4 and find the password for Leviathan 5.  

---

## 🔐 Credentials  

- **Username:** `leviathan4`  
- **Host:** `leviathan.labs.overthewire.org`  
- **Port:** `2223` (SSH)  
- **Password:** `WG1egElCvO`  

---

## 🖥️ Commands Used  

```bash
leviathan4@leviathan:~$ ls -la
total 24
drwxr-xr-x   3 root root       4096 Aug 15 13:17 .
drwxr-xr-x 150 root root       4096 Aug 15 13:18 ..
-rw-r--r--   1 root root        220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root root       3851 Aug 15 13:09 .bashrc
-rw-r--r--   1 root root        807 Mar 31  2024 .profile
dr-xr-x---   2 root leviathan4 4096 Aug 15 13:17 .trash
leviathan4@leviathan:~$ cd .trash
leviathan4@leviathan:~/.trash$ ls -l
total 16
-r-sr-x--- 1 leviathan5 leviathan4 14940 Aug 15 13:17 bin
leviathan4@leviathan:~/.trash$ ./bin
00110000 01100100 01111001 01111000 01010100 00110111 01000110 00110100 01010001 01000100 00001010 
leviathan4@leviathan:~/.trash$ mkdir /tmp/amro.xyz
leviathan4@leviathan:~/.trash$ ./bin > /tmp/amro.xyz/test.txt
leviathan4@leviathan:~/.trash$ cat /tmp/amro.xyz/test.txt
00110000 01100100 01111001 01111000 01010100 00110111 01000110 00110100 01010001 01000100 00001010 
leviathan4@leviathan:~/.trash$ python3
Python 3.12.3 (main, Jun 18 2025, 17:59:45) [GCC 13.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> x = open("/tmp/amro.xyz/test.txt").read().split()
>>> print(x)
['00110000', '01100100', '01111001', '01111000', '01010100', '00110111', '01000110', '00110100', '01010001', '01000100', '00001010']
>>> final_text = ""
>>> for b in x:
...     final_text += chr(int(b,2))
... 
>>> print (final_text)
0dyxT7F4QD



```
___

## 💡 Theory
```bash
leviathan4@leviathan:~/.trash$ cat /tmp/amro.xyz/test.txt
00110000 01100100 01111001 01111000 01010100 00110111 01000110 00110100 01010001 01000100 00001010 
leviathan4@leviathan:~/.trash$ python3
Python 3.12.3 (main, Jun 18 2025, 17:59:45) [GCC 13.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> x = open("/tmp/amro.xyz/test.txt").read().split()
>>> print(x)
['00110000', '01100100', '01111001', '01111000', '01010100', '00110111', '01000110', '00110100', '01010001', '01000100', '00001010']
>>> final_text = ""
>>> for b in x:
...     final_text += chr(int(b,2))
... 
>>> print (final_text)
0dyxT7F4QD
```
int(some_text,base) convert for example base2 (binary) to integer
chr(integer_value) conver integer value into ASCII 
```bash
leviathan4@leviathan:~/.trash$ ./bin | xxd -b -r
dyxT7F # truncated result not 0dyxT7F4QD
why ? beacause xxd -b requires special format (dumb)
That’s the xxd -b dump.
It has three columns:

Offset (hex) → 00000000:

The position of the first byte in this line (starts at 0).

Binary values → 01001000 01000101 and so on 

Each byte shown as 8 bits.

ASCII preview → HE and so on 

Printable characters shown on the right. Non-printables show as .
```
```bash
note that echo "HE" : is trated as "HE/n"
```
using xxd -r -b requires a special format or dump like offset-binary value - ASCII preview
___

## 📤 Output
```bash
0dyxT7F4QD
```
