# Natas Level 0 

## 🧠 Goal

Find password to the next level

---

## 🔐 Credentials

- **Username:** `natas0`  
- **Host:** `natas0.natas.labs.overthewire.org`   
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
Each website is rendered by the web browser based on the code (HTML, CSS, JS) requested by server. It is possible to look at this source code. There are multiple different ways to do this:

    Using a command line tool for web requests (such as Curl or wget)
    Right-clicking and selecting ‘View Page Source’ (only HTML)
    Opening the inspector of the developer tools of your chosen browser. (Often done with F12)

The Hypertext Markup Language (HTML) is the bones of every website. It contains the content and structure of a website. The basics of HTML are easy to learn and I would recommend you, to do so for this wargame. (Check out W3Schools) for a quick Tutorial/Overview. While HTML is not a programming language, it does have a comment tag. This allows for the insides of this tag to not be rendered by the browser and will therefore not be seen by users, who do not look at the source code.
___

## 📤 Output
```bash
0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq
```
