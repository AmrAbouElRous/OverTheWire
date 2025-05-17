# Natas Level 10 -> 11 

## 🧠 Goal

Find password to the next level

---

## 🔐 Credentials

- **Username:** `natas11`  
- **Host:** `natas11.natas.labs.overthewire.org`   
- **Port:** `80` (HTTP)  
- **Password:** `UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk` 

---

## 🖥️ Commands Used
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas11:UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk natas11.natas.labs.overthewire.org
<h1>natas11</h1>
<div id="content">
<body style="background: #ffffff;">
Cookies are protected with XOR encryption<br/><br/>


<form>
Background color: <input name=bgcolor value="#ffffff">
<input type=submit value="Set color">
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>

```
### 3 ways to post

```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas11:UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk natas11.natas.labs.overthewire.org --data "bgcolor=#ffffee&submit=Set color" 
```
or
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas11:UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk natas11.natas.labs.overthewire.org --data "bgcolor=%23ffffee&submit=Set%20color"
```
or 
```bash
┌──(amro㉿amro)-[~]
└─$ curl -u natas11:UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk "http://natas11.natas.labs.overthewire.org/?bgcolor=%23ffffee&submit=set%20Color"
```

```php
<?php
// Theory:
// if plain ^ key = encrypted
// so palin ^ encrypted = key

$plain=json_encode (array( "showpassword"=>"no", "bgcolor"=>"#ffffff"))     ;echo "$plain\n";
$cookie ='HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg=';
$decoded = base64_decode($cookie); echo "$decoded\n";

function xor_encrypt($in) {
    $plain=json_encode (array( "showpassword"=>"no", "bgcolor"=>"#ffffff"));
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $plain[$i % strlen($plain)];
    }

    return $outText;
}
$key =xor_encrypt($decoded) ; echo "$key \n";
$key ='eDWo';

$modified_plain = json_encode (array( "showpassword"=>"yes", "bgcolor"=>"#ffffff"))     ;echo "$modified_plain\n";

function xor_encrypt_2($in) {
    $key ='eDWo';
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}
$modified_cookie = xor_encrypt_2($modified_plain);

echo base64_encode($modified_cookie);
// HmYkBwozJw4WNyAAFyB1VUc9MhxHaHUNAic4Awo2dVVHZzEJAyIxCUc5

// now go change the cookie and refresh page
// The password for natas12 is yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB

?>

```
___

## 💡 Theory
```bash

```
___

## 📤 Output
```bash
yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB
```
