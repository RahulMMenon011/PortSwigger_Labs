This lab has a stock check feature which fetches data from an internal system.

To solve the lab, change the stock check URL to access the admin interface at http://localhost/admin and delete the user carlos.

### Solution

Used the check stock button, captured the http request via burp intruder

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a51d7e86-de1e-4bbb-bfb9-5ac64549c94c)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ec833abb-8f99-4473-b3de-311151fd79e4)

By modifing the stock API parameter to `http://localhost/admin` was able to display the admin interface, also found the URL to delete the user carlos

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d4774948-84a2-41b0-a40c-5c6b0a572363)

Deleted the user carlos succesfully and solved the lab

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/2cd30d70-a270-437c-83c6-efbc062d6bbe)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/79ab0c5d-2693-4a3c-93f7-cfe772b49456)
