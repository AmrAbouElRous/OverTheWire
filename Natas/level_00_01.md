# Natas Level 0 → Level 1 

## 🧠 Goal

Find password to the next level

---

## 🔐 Credentials

- **Username:** `natas1`  
- **Host:** `natas1.natas.labs.overthewire.org`   
- **Port:** `80` (HTTP)  
- **Password:** `0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq` 

---

## 🖥️ Commands Used

```bash
└─$ curl -u natas1 http://natas1.natas.labs.overthewire.org
Enter host password for user 'natas1':
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas1", "pass": "0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq" };</script></head>
<body oncontextmenu="javascript:alert('right clicking has been blocked!');return false;">
<h1>natas1</h1>
<div id="content">
You can find the password for the
next level on this page, but rightclicking has been blocked!

<!--The password for natas2 is TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI -->
</div>
</body>
</html>

```
___

## 💡 Tips
```bash

```
___

## 📤 Output
```bash
TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI
```
