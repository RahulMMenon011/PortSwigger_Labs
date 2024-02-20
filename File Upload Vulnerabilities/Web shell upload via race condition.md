This lab contains a vulnerable image upload function. Although it performs robust validation on any files that are uploaded, it is possible to bypass this validation entirely by exploiting a race condition in the way it processes them.

To solve the lab, upload a basic PHP web shell, then use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter

### Soultuion
Successfully uploaded an image to the file server

Created a php file with the exploit and tried uploading the php file and the server prevented the upload

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/4253b9d7-857d-4498-b2e2-c534b09636c0)

Sent the GET and POST request with the exploit.php file to intruder

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/03b442a8-1993-4e9f-8cb1-6aa556509fa3)

Made the Adjustments

* Attack Type: Sniper

* Payload Type: Null Payloads (We simply want to send the requests as-is without any modifications)

* Payload Settings: Continue indefinitely

* Payload Encoding: Uncheck the box

Then ran both the attacks simultaneously

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/c011758d-d1f0-4225-953b-a35004e2c546)

In the response tab of GET request attack we could see the HTTP 200 code along with the secret

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/3e166ce8-0f79-4e50-b910-d996303ca9f0)

Lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7d89ecd0-8ae4-47d5-9477-d7ba3412b405)

