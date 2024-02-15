This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs a SQL query containing the value of the submitted cookie.

The SQL query is executed asynchronously and has no effect on the application's response. However, you can trigger out-of-band interactions with an external domain.

The database contains a different table called users, with columns called username and password. You need to exploit the blind SQL injection vulnerability to find out the password of the administrator user.

To solve the lab, log in as the administrator user

### Solution

captured the get request and changed the tracking id 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/5a01cc95-bb8d-42b8-98f5-f02b10b06147)

edited the payload 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/2f2e8203-63f2-4b32-a640-53c644cec008)

got the password from collaborator

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8714abaa-6bfe-4f18-8ef8-f7863bb8e2c6)

lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d7c3a93f-d877-4b3c-b0da-a5a4f4d7b5ec)

