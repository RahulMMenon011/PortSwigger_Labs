This lab contains a vulnerable image upload function. Certain file extensions are blacklisted, but this defense can be bypassed due to a fundamental flaw in the configuration of this blacklist.

To solve the lab, upload a basic PHP web shell, then use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter

### Solution

Tried uploading the php file, but it was bolcked by the server

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ffc2a35d-71ba-4502-9cdf-795fd18b3739)

Mapped an arbitrary extension `.l33t` to the executable MIME type 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/004560fb-7b64-4a89-8726-91e58096d50c)

The exploit has been successfully uploaded now

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d702668b-a9c4-4c93-9805-4c5560cafa77)

switched to the GET tab and recovered the secret, lab completed succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/fcf50a0d-2b83-4f72-8981-8e3c475689b5)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0a0aa224-b21f-4e97-beab-c26003800828)
