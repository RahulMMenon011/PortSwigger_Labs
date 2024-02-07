This lab contains a blind OS command injection vulnerability in the feedback function.

The application executes a shell command containing the user-supplied details. The output from the command is not returned in the response

we will exploit the blind OS command injection vulnerability to cause a 10 second delay.

### Solution

Submitting a feedback and capturing the http response

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0ae6c761-72b9-4726-843c-5b4e0c5c89d5)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a9e2f1ca-f9d9-4e10-a6a6-f48b4ad52d6b)

add the command `||ping+-c+10+127.0.0.1||` to enable time delay to successfully solve the lab

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/14f3e437-7c47-4bef-864b-5b5be4d3c957)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/2282454e-005c-4c41-afc9-94dc591f3f33)


