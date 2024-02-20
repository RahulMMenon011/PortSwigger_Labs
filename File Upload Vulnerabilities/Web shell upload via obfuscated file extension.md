This lab contains a vulnerable image upload function. Certain file extensions are blacklisted, but this defense can be bypassed using a classic obfuscation technique.

To solve the lab, upload a basic PHP web shell, then use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter

### Solution

Tried uploading the exploit php script but the server denied the access

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d486fa92-c24a-47db-b31a-5ba9a867013e)

Tried changing the php file to `myexploit.php%00.jpg`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/cec9a151-1a9a-4fdd-aedb-5e073602df00)

Obfuscated the file extensions successfully and uploaded the file.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ca51a11e-daed-4091-8192-ab841852304d)

Secret is found and completed lab succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/dafe9b12-1ad1-412e-9db9-a08ae7e3fdc2)
