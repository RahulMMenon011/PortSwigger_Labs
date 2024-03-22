![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/29aeb71b-4ebd-49da-a13d-49088d1caf18)

### Solution

Initally logged in as admin and promoted the user carlos

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/21a397d1-eeaa-4e98-8ff6-d1a950cdb96f)

the corresponding http request could be seen, sent it to repeater

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/38f0ff82-5b22-4203-b3ec-a8befb718840)

log out as admin and log in as wiener account, the non admin account that we want to promote

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/aa36d23e-8d62-4814-871a-894e0dae6e90)

click on my account option and check the http request

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b262dd01-3eaf-4c71-bfb1-8d07e2463caa)

now copy the session id and paste it on the previous admin role request that we sent to the repeater, we are making it such that our account `wiener` sent the admin role request

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6c1bacab-6999-42f5-9dfc-3188208a263a)

it says unauthorized, now we change the request method

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0885aeb2-539d-45c6-a352-ea6561e75f9f)

changed the request method to GET and username to wiener, was able to upgrade user. Lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/fe0fc076-0439-4c10-91d5-16b2ef14892b)

