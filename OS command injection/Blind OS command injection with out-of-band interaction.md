This lab contains a blind OS command injection vulnerability in the feedback function.

The application executes a shell command containing the user-supplied details. The command is executed asynchronously and has no effect on the application's response. It is not possible to redirect output into a location that you can access. However, you can trigger out-of-band interactions with an external domain.

To solve the lab, exploit the blind OS command injection vulnerability to issue a DNS lookup to Burp Collaborator

### Solution

Submitted a feedback in the feeback section and captured the post request in burp.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a1014b49-eae5-4260-8064-942dbef917f8)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/44eb8121-5ef2-4be4-a636-c124f1cc6eec)

Now modified the email field

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/68317e8b-f396-477b-9910-01a6b2506196)

inserted the burp collaborator payload

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/eafa1ebe-684d-4066-9842-f23b779e983b)

Burp collaborator tab

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/188c4060-0c62-49b0-a360-d5667fbbb908)

Lab solved succesfully.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e281bf6b-c0be-46b6-8998-86e4b944e079)

