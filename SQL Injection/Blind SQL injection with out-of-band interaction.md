This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs a SQL query containing the value of the submitted cookie.

The SQL query is executed asynchronously and has no effect on the application's response. However, you can trigger out-of-band interactions with an external domain.

To solve the lab, exploit the SQL injection vulnerability to cause a DNS lookup to Burp Collaborator.

### Solution

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ccfae494-a22e-4218-9362-2a8aa8f95799)

modified the intercepted get request tracking id and inserted the collaborator payload

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d669fc46-05f6-46e7-ba11-62e9c81ad2aa)

DNS lookup completed succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b475668b-ff32-4a43-9442-b98067944bc2)
