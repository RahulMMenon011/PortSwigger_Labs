This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs a SQL query containing the value of the submitted cookie.

The results of the SQL query are not returned, and the application does not respond any differently based on whether the query returns any rows or causes an error. However, since the query is executed synchronously, it is possible to trigger conditional time delays to infer information.

The database contains a different table called users, with columns called username and password. You need to exploit the blind SQL injection vulnerability to find out the password of the administrator user.

To solve the lab, log in as the administrator user.

### Solution

intercepted the get request and changed the tracking id `x'%3BSELECT+CASE+WHEN+(1=1)+THEN+pg_sleep(10)+ELSE+pg_sleep(0)+END--`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b420b7d4-4a14-46f9-ae64-92b25f7337a5)

10 sec delay occured so query was valid.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a5beb7c4-e894-4d61-be9a-74b883e6332b)

slightly changed the query, now there is no 10 sec delay.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0042a728-685a-464a-8ba7-44fc8305a44f)

modified the value, now we can be sure that there exist a user called `administrator` in the table 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/3211a115-ff02-4cb6-98aa-2644a5a9d62f)

modified the query to get the password

the password length is greater than 1, now we will find the password length using intruder.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8e63405d-c620-40f6-894c-97e16b74a33c)

the password is between 1 and 25, we can use intruder to find the correct length of the password.

### finding out password length

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/1f0b257e-bb29-4cc6-862b-a3afe2238184)

from this we could find out the password length is 20

got the password using clusterbomb attack

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/32a373fd-3147-48e6-aad5-ce52af0dfae2)

logged in as administrator and completed lab succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d6da4eca-c351-4780-a7d8-72d4a614f61e)


