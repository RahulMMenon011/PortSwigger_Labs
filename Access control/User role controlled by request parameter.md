![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/106e5903-3da9-4df4-87cc-ba5abea2a990)

### Solution

Tried accessing the admin page directly by modifying the URL but access was denied.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/51a9510c-9a15-4736-ae57-ca145708b69d)

Logged in using credentials while intercept was turned on,captured the response request in the intercepter

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d2da7c0d-bfde-47b3-9e10-52028b76b7af)

changed the `admin=false` to true in the cookie and sent the request

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0849a3ae-a207-49b3-9b7f-97677866c9ec)

changed the cookie of original web page using inspect element to gain admin panel access

![Screenshot 2024-03-14 202954](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a40ee2bf-6208-401f-9416-252f4a45b03b)

deled user and solved the lab

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/bc782a9c-daa8-4ffd-ae16-e869a3b82ceb)
