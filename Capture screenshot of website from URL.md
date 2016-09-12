---
title: Capture screenshot of website from URL
tip-number: 11
tip-username: Vijayanand
tip-username-profile: https://github.com/vpvijayanand
tip-description: Capture screenshot of website from URL.

---

We will see how to grab screen shot for a given URL using PHP curl.  
I am using screenshotmachine.com website API to do this. 
You need to create an account in this website to get the accountKey. 
You can use the accountKey in the below code and enjoy taking screenshot. 


<b>Url</b>
```php
http://localhost/index.php?url=vijayanand.me
```
<b>Code
File Name : index.php</b>
```php
<?php
	$screenImage = date('Y-m-d-H-i-s').'.png';
        $accountKey = 'your Key'; // replace with your account key
        $ch = curl_init('http://api.screenshotmachine.com/?key='.$accountKey.'&size=M&format=png&url='.$_GET['url']);
        $f = fopen('images/'.$image, 'wb');
        curl_setopt($ch, CURLOPT_FILE, $f);
        curl_setopt($ch, CURLOPT_HEADER, 0);
        curl_exec($ch);
        curl_close($ch);
        fclose($f);
?>
	<img src="images/<?php echo $screenImage ?>" />
```
