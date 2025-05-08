# Natas Level 0

## 🧠 Goal

Natas Level 0

Username: natas0
Password: natas0
URL:      http://natas0.natas.labs.overthewire.org
---

## 🔐 Credentials

- **Username:** `natas0`  
- **Host:** `http://natas0.natas.labs.overthewire.org`   
- **Port:** `80` (HTTP)  
- **Password:** `natas0` 

---

## 🖥️ Commands Used

```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas0 http://natas0.natas.labs.overthewire.org      
Enter host password for user 'natas0':
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas0", "pass": "natas0" };</script></head>
<body>
<h1>natas0</h1>
<div id="content">
You can find the password for the next level on this page.

<!--The password for natas1 is 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq -->
</div>
</body>
</html>

```
___

## 💡 Tips
```bash
curl -u natas0:natas0 http://natas0.natas.labs.overthewire.org

```
___

## 📤 Output
```bash
0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq
```
