# Bandit Level 18 → Level 19

## 🧠 Goal

The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.
Commands you may need to solve this level

ssh, ls, cat

---

## 🔐 Credentials

- **Username:** `bandit18`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`

---

## 🖥️ Commands Used

```bash
┌──(amro㉿amro)-[~]
└─$ ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
ls        
readme
cat readme
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

or you can do
```bash
┌──(amro㉿amro)-[~]
└─$ ssh bandit18@bandit.labs.overthewire.org -p 2220 ls
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
readme
                                                                                                     
┌──(amro㉿amro)-[~]
└─$ ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```
___

## 💡 Tips

In the walkthrough to Level 0 I have given a short introduction to SSH. Something I have not mentioned is that SSH does not just allows us to log into a machine remotely, but it also allows remote execution of commands by adding the commands after the common SSH expression.
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash
```
___

## 📤 Output
```bash
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

