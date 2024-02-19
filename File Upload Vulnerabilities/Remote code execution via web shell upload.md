This lab contains a vulnerable image upload function. It doesn't perform any validation on the files users upload before storing them on the server's filesystem.

To solve the lab, upload a basic PHP web shell and use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter

### Solution

Uploaded an avatar in the user profile section

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/050c491f-4fd7-4f49-bee1-fdf4b329c8c5)

sent the POST request which uploaded the image and GET request which views the image to the repeater

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a2c598d3-ab80-4a24-a203-856312a322d9)

changed the type of file to php and added the payload to the file, also renamed the file in the get request

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/5a267f21-e388-4dd9-a356-515e54f186de)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f6c1e456-e8ae-4c30-b190-5fa26bf1f49c)

Uploaded the payload and secret is uncovered

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8a63e8e8-6d21-4d46-9d59-f78cea8f74cd)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/4ce8b662-9523-423b-a6d2-26a01b334897)

lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/582f97d8-dab0-472b-92e9-862413f2584e)


