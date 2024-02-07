This lab contains a path traversal vulnerability in the display of product images.

The application transmits the full file path via a request parameter, and validates that the supplied path starts with the expected folder.

To solve the lab, retrieve the contents of the /etc/passwd file.

### Solution

Use Burp to intercept and modify a request that fetches product image

![WhatsApp Image 2024-02-07 at 12 12 00_9681424a](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/9b34bdb1-e4fb-4f8d-92ad-5a5c05e7460d)

Lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/74536c16-3e7a-44bf-bec5-9e386776a462)
