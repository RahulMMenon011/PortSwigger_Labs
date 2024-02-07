This lab contains a path traversal vulnerability in the display of product images.

The application blocks traversal sequences but treats the supplied filename as being relative to a default working directory.

To solve the lab, retrieve the contents of the /etc/passwd file.

The image is opened in new tab and that http request is intercepted.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ea9e7dd1-171a-4fca-9bd6-772899b2cce4)

used the payload `/etc/passwd` and we recived the result.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a959e3b0-dbff-4f8b-9894-c90da0382cca)

lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0a0c1169-d60a-4efd-bff3-160f4fcd62bd)


