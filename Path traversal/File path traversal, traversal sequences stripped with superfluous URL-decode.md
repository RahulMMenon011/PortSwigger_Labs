This lab contains a path traversal vulnerability in the display of product images.

The application blocks input containing path traversal sequences. It then performs a URL-decode of the input before using it.

To solve the lab, retrieve the contents of the /etc/passwd file

### Solution

We used the double URL encoding `%252e%252e%252f` for `../`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/01eb8fd4-1d7e-4a48-b7cd-5353f436881b)

Lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/da59b1c3-2aa2-4bb7-9363-d48f4f19466b)

