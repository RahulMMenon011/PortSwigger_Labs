This lab contains a path traversal vulnerability in the display of product images.

To solve the lab, retrieve the contents of the /etc/passwd file.

### Solution

Use Burp to intercept and modify a request that fetches product image

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/db40890c-aa4b-4c6e-8c1f-0f3d6bb3ffe6)

Now give the path `../../../etc/passwd` in the location of the file name

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6e6f7614-fd2d-4db8-a3ce-8d7d90d66010)

we are able to access the passwd file.

Lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/031cc864-1b2f-4710-9874-a20f03a3c48e)
