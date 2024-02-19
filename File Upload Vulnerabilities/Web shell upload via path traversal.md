This lab contains a vulnerable image upload function. The server is configured to prevent execution of user-supplied files, but this restriction can be bypassed by exploiting a secondary vulnerability.

To solve the lab, upload a basic PHP web shell and use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter

### Solution

Uploaded the image, sent the GET and POST request containing the image to repeater

created exploit.php and injected the paylod. it was noted that instead of executing the command the command was displayed in plain text.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/fe09a9fb-f807-4d73-842f-6c9fe6022f0f)

By trying `../myexploit.php` it can be noted that the server is stripping the directory traversal sequence

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/30040e61-687c-423c-b431-ad59c6134a13)

trying the URL encoding

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0053f10a-10ee-4fda-8125-feb383260cd8)

successfully uploaded after url encoding `..%2fmyexploit.php`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f072637f-6d6a-4c92-96f7-af210a26d856)

Secret found and lab solved sucessfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/717a23aa-482f-4ef8-b05b-58dd20111ea2)
