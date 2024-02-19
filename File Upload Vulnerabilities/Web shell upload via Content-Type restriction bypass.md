This lab contains a vulnerable image upload function. It attempts to prevent users from uploading unexpected file types, but relies on checking user-controllable input to verify this.

To solve the lab, upload a basic PHP web shell and use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter

### Solution

Captured the GET and POST request after uploading the avatar, edited the image file to php file with payload

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/64032c1d-f8b9-4b94-b863-ec5a0d287a7a)

uploaded the php file and got the secret

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b34c94a2-1701-4bb0-8fa0-7b2ac8402a15)

lab solved succesfully

![Screenshot 2024-02-19 203104](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/89436844-ef25-4da7-9751-627436b3c980)
