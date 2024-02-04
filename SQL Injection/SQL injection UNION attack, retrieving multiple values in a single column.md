This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response so you can use a UNION attack to retrieve data from other tables.

The database contains a different table called users, with columns called username and password.

To solve the lab, perform a SQL injection UNION attack that retrieves all usernames and passwords, and use the information to log in as the administrator user.

We used the payload `'UNION+SELECT+NULL,'a'--`

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/bb46bc4b-2193-4bbd-be6c-c798abe1e6cf)

Here only the second column returns the text data.

Now used the payload `'UNION+SELECT+NULL,username||'~'||password+FROM+users--` to 

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/057c6bd7-cbf3-490f-844f-feb144bfdcd9)

Tried signing in with the password

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/a13ffcc5-9bab-4712-8f49-1c2dbc9b1cc8)

Successfully logged in

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/ccec7350-0d7e-4f8a-8031-aec4a70957e1)



