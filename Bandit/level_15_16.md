# Bandit Level 15 → Level 16

## 🧠 Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

Commands you may need to solve this level

ssh, telnet, nc, ncat, socat, openssl, s_client, nmap, netstat, ss
Helpful Reading Material

    Secure Socket Layer/Transport Layer Security on Wikipedia
    OpenSSL Cookbook - Testing with OpenSSL


---

## 🔐 Credentials

- **Username:** `bandit15`
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Password:** `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`

---

## 🖥️ Commands Used

```bash
bandit15@bandit:~$ echo 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo | openssl s_client -connect localhost:30001 -quiet
#-queit show only the data exchanged over the connection, making the output cleaner and easier
```

Or do this instead

``` bash

#openssl command [ options ... ] [ parameters ... ]
openssl s_client -connect localhost:30001
#then enter password in the next prompot
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```
___

## 💡 Tips
How to usefully search ?
```bash
#read quick
man openssl
# when u find something related man it then echo notes for you
man openssl s_client
echo [-connect host:port]
openssl s_client -connect bandit.labs.overthewire.org:30001
#or
openssl s_client -connect localhost:30001
				
```


 nc (netcat)

    Used for: Plain, raw TCP/UDP communication.

    Security: ❌ No encryption at all.

    Use case: Good for basic connections, debugging, port scanning, transferring files over unencrypted channels.

```bash
echo "hello" | nc localhost 30000
```

This works only if the service at port 30000 is plain text (no encryption).

🔐 openssl s_client

    Used for: Encrypted SSL/TLS connections.

    Security: ✅ Full SSL/TLS encryption.

    Use case: Required when the server expects secure (TLS) communication — like HTTPS, SMTPS, FTPS, etc.
```bash
echo "password" | openssl s_client -connect localhost:30001 -quiet
```

This is what you need for Bandit Level 15 → 16, because the level specifically requires SSL/TLS.

___

## 📤 Output
```bash
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

