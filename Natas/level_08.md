# Natas Level 7 -> 8 

## 🧠 Goal

Find password to the next level

---

## 🔐 Credentials

- **Username:** `natas8`  
- **Host:** `natas8.natas.labs.overthewire.org`   
- **Port:** `80` (HTTP)  
- **Password:** `xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q` 

---

## 🖥️ Commands Used
login
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas8:xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q natas8.natas.labs.overthewire.org
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas8", "pass": "xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q" };</script></head>
<body>
<h1>natas8</h1>
<div id="content">


<form method=post>
Input secret: <input name=secret><br>
<input type=submit name=submit>
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```
submit any value
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas8:xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q natas8.natas.labs.overthewire.org \
--data "secret=ggg&submit=submit" | html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1026  100  1002  100    24   4311    103 --:--:-- --:--:-- --:--:--  4422
****** natas8 ******
Wrong secret
Input secret:[secret              ]
[Submit]
View sourcecode

```
view
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas8:xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q natas8.natas.labs.overthewire.org/index-source.html |html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3508  100  3508    0     0  15325      0 --:--:-- --:--:-- --:--:-- 15318
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/
css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-
ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/
wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></
script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas8", "pass": "<censored>" };</
script></head>
<body>
<h1>natas8</h1>
<div id="content">

<?

$encodedSecret = "3d3d516343746d4d6d6c315669563362";

function encodeSecret($secret) {
    return bin2hex(strrev(base64_encode($secret)));
}

if(array_key_exists("submit", $_POST)) {
    if(encodeSecret($_POST['secret']) == $encodedSecret) {
    print "Access granted. The password for natas9 is <censored>";
    } else {
    print "Wrong secret";
    }
}
?>

<form method=post>
Input secret: <input name=secret><br>
<input type=submit name=submit>
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>

```
bin2hex <- strrev <- base_64_encode
 
Reverse engineering 
 
hex2bin -> strrev -> base64_decode

```bash
┌──(amro㉿amro)-[~]
└─$ encodedSecret="3d3d516343746d4d6d6c315669563362"

┌──(amro㉿amro)-[~]
└─$ echo $encodedSecret | xxd -r -p
==QcCtmMml1ViV3b 

┌──(amro㉿amro)-[~]
└─$ echo $encodedSecret | xxd -r -p | rev
b3ViV1lmMmtCcQ==                                                                                                     
┌──(amro㉿amro)-[~]
└─$ echo $encodedSecret | xxd -r -p | rev | base64 -d
oubWYf2kBq 
```
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas8:xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q natas8.natas.labs.overthewire.org \
--data "secret=oubWYf2kBq&submit=submit" | html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1096  100  1065  100    31   4605    134 --:--:-- --:--:-- --:--:--  4744
****** natas8 ******
Access granted. The password for natas9 is ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t
Input secret:[secret              ]
[Submit]
View sourcecode
```
___

## 💡 Theory

bin2hex <- strrev <- base_64_encode
 
Reverse Engineering 
 
hex2bin -> strrev -> base64_decode


___

## 📤 Output
```bash
ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t
```
