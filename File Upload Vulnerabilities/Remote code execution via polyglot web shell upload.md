This lab contains a vulnerable image upload function. Although it checks the contents of the file to verify that it is a genuine image, it is still possible to upload and execute server-side code.

To solve the lab, upload a basic PHP web shell, then use it to exfiltrate the contents of the file /home/carlos/secret. Submit this secret using the button provided in the lab banner.

You can log in to your own account using the following credentials: wiener:peter

### Soultion

Tried uploading the exploit php code but the server denied the access saying it is not an image file.

![Screenshot 2024-02-20 092612](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/20936436-f421-4e6a-bf7e-a910882c351c)

Created a Polygot.php file by manipulating the metadata of an existing file to contain the php code using exif tool

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6887bcb6-b99c-424d-8d29-14c0bc51e10b)

Uploaded the Polygot.php file

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8869fd75-d256-46ef-aa33-85e4a9ec0d54)

In the GET request of Polygot.php we are able to find the secret inside the metadata between the START and END section

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d3a4af0a-87c3-4246-952c-95ba63852d1f)

Succesfully completed the lab

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/99cb21d0-e26f-40ab-b9e8-4f6d82d2b784)




