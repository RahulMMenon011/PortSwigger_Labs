![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/687def91-79fc-46bf-9135-53a8bab759a6)

### Solution

logging in using the given credentials and modifying the http request to set role id to `2`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/fe958126-b8c8-4c38-856a-9da2485cfc05)

updated the email id and captured the http request 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/13becb7e-c87e-49e1-b5dd-3a893fae56b0)

It can be seen that the role id is `1`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8bd66947-8e05-4e31-b602-28ccddf5dbec)

added the keyword `roleid=2`, the server accepted the request 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7776de8e-917d-44ce-b514-dca3a9153f49)

Opened the request in browser and admin panwl could be seen now

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/55d30dfa-707a-4750-8029-c1c8193d7841)

Deleted user carlos and solved lab succesfully

![Screenshot 2024-03-21 225240](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/63c1a5d0-727b-40d3-9b99-e6e4876b3f59)

![Screenshot 2024-03-21 225254](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d7cc1003-37c0-4ec6-b6ad-fbc45a770747)
