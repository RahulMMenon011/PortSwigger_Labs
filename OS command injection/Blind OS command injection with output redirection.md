This lab contains a blind OS command injection vulnerability in the feedback function.

The application executes a shell command containing the user-supplied details. The output from the command is not returned in the response. However, you can use output redirection to capture the output from the command. There is a writable folder at:

`/var/www/images/`

The application serves the images for the product catalog from this location. You can redirect the output from the injected command to a file in this folder, and then use the image loading URL to retrieve the contents of the file.

execute the whoami command and retrieve the output to solve the lab

Filled the submit form and captured the http response

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7598b92c-1440-4d74-bb97-9b9815bcf0cf)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7c03a619-8240-4b78-bdc2-0027d9d64416)

add the command `||whoami > /var/www/whoami.txt||` in the email feild to create the output file

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8dd9e006-dc30-4aa9-b592-1552dda76c83)

now open an image in new tab with intercept on and capture the request, change the filename to the text file that we created.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/386fca9d-27c1-439f-b34d-96caa7d16053)

lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/74a04d6e-2e9a-4cff-bd2c-a443f216a761)

