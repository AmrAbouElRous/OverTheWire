# Bandit Level 20 → Level 21

## 🧠 Goal

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think
Commands you may need to solve this level

ssh, nc, cat, bash, screen, tmux, Unix ‘job control’ (bg, fg, jobs, &, CTRL-Z, …)

---

## 🔐 Credentials

- **Username:** `bandit20`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`

---

## 🖥️ Commands Used

```bash
tmux
```
ctrl + B then % 
ctrl + B then move with keyboard
```bash
bandit20@bandit:~$ ls -l                          │bandit20@bandit:~$ nc -l 4444
total 16                                          │0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
-rwsr-x--- 1 bandit21 bandit20 15608 Apr 10 14:23 │EeoULMCra2q0dSkYj561DX7s1CpBuOBt
suconnect                                         │bandit20@bandit:~$ 
bandit20@bandit:~$ ./suconnect 4444               │
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO            │
Password matches, sending next password           │
bandit20@bandit:~$          
```
___

## 💡 Tips

[tmux in Linux - GeeksforGeeks](https://www.geeksforgeeks.org/tmux-in-linux/)

[Practical uses of nc (netcat) command in Linux - GeeksforGeeks](https://www.geeksforgeeks.org/practical-uses-of-ncnetcat-command-in-linux/)

```bash
⚡ Simple Analogy: Phone Call

    nc -l 12345 = "I'm waiting for a call on line 12345"

    ./suconnect 12345 = "I'm calling line 12345 and saying something"

    You = the operator who hears what’s said and repeats it

    If you repeat it right → you get a reward!

💡 Important Note

    nc listens

    suconnect connects

    The port number must match on both

    You are the one who "echoes" the message back by typing it
    
    +-------------------+                          +---------------------+
|    ./suconnect    | -- connect to 4444 -->   |     nc -l 4444      |
|  (client)         |                          |   (acting as server)|
|  Sends password   |                          | Receives it         |
|  Waits for reply  | <--- send password back--| You type it manually|
+-------------------+                          +---------------------+


```
___

## 📤 Output
```bash
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

