This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables. To construct such an attack, you need to combine some of the techniques you learned in previous labs.

The database contains a different table called users, with columns called username and password.

To solve the lab, perform a SQL injection UNION attack that retrieves all usernames and passwords, and use the information to log in as the administrator user.

First determine the number of columns that are being returned by the query and which columns contain text data.

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/e0a34ff4-281e-44cc-8385-f762882e8e5e)

We were able to identify that two columns are being returned by the query which contains the text data.

Now we have to retrive the contents of the users table

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/de1a0fe4-e8d6-4d4b-8edd-f4b0045edfff)

By using the payload `'UNION+SELECT+username,+password+FROM+users--` we were able to retrive the user data form the table

Now tried to log in as the administrator using the corresponding password

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/b99b54c1-a98e-4248-94bb-fa4b30c7bbf9)

Successfully logged in

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/64261884-c018-45ec-9c6c-afa550563aaf)


