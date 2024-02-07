This lab contains a path traversal vulnerability in the display of product images.

The application validates that the supplied filename ends with the expected file extension.

To solve the lab, retrieve the contents of the /etc/passwd file.

### Solution

Use Burp to intercept and modify a request that fetches product image

give the payload `../../../etc/passwd%00.png` 

the .png will be omitted as we are giving `%00`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e751082d-44ce-4c12-ad60-77d4a6c32bbe)

Lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7c9298e6-3d16-4442-a100-b070f79c8cbd)

