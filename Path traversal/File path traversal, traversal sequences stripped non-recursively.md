This lab contains a path traversal vulnerability in the display of product images.

The application strips path traversal sequences from the user-supplied filename before using it.

To solve the lab, retrieve the contents of the /etc/passwd file.

### Solution

give the payload  `....//....//....//etc/passwd` 

we will recive the result

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/51c83c53-801a-4be4-88a5-240dbee2292b)

lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/71bcf859-fd87-47b9-a281-c0408d9ab81c)
