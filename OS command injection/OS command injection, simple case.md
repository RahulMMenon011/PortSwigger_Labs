This lab contains an OS command injection vulnerability in the product stock checker.

The application executes a shell command containing user-supplied product and store IDs, and returns the raw output from the command in its response.

To solve the lab, execute the whoami command to determine the name of the current user.

Using Burp Suite intercept and modify a request that checks the stock level inside the product details page.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f49a1973-a981-441e-951d-a7ee8a1c99f8)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8112156a-d97b-40f4-8890-a06f87d921c3)

Modify the storeID parameter, giving it the value `1|whoami`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/90524502-44a0-4b81-abf8-ba7721711a08)
