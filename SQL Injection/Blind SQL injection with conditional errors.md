This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs a SQL query containing the value of the submitted cookie.

The results of the SQL query are not returned, and the application does not respond any differently based on whether the query returns any rows. If the SQL query causes an error, then the application returns a custom error message.

The database contains a different table called users, with columns called username and password. You need to exploit the blind SQL injection vulnerability to find out the password of the administrator user.

To solve the lab, log in as the administrator user.

Captured the http page in burpsuite

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/939b26f8-8ddc-42e3-a97d-303a4660cf28)

appending the `'` to the tracking id and verify that error message is shown

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ae8b1bae-f2c4-434f-8c55-bdd4fde6441a)

giving 2 `'` the error is gone so the syntax is right

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/9948e1fd-f7a3-41e2-b8ba-2d469451d7d5)

now giving `''||(SELECT ''FROM )||'` we get error

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a079ecfd-cea4-454c-a4e9-718d5531d4b1)

now giving `''||(SELECT ''FROM dual)||'` the error is gone so the syntax is correct.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/25613ed2-63fb-4677-ad7a-bdea4c9e9537)

No error we got respones.So it is orcal database.

the payload `'||(SELECT '' FROM not-a-real-table)||'` gives error because the table does not exist

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b8054eba-55bf-479e-b96c-bebadd3a263b)


### Check Whether the users table is present 

`'||(SELECT '' FROM users WHERE ROWNUM = 1)||'` 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/93036487-9992-436f-9a5d-a66b07aaeb65)

No error so there exist a table users.

### Check Whether the username administrator is present in users table

the payload `'||(SELECT CASE WHEN (1=1) THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'` is given

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/640cb04a-354b-48ef-8bfb-ebc1ab1f47c7)

We receive an error. means the condition is TRUE and username administrator is present in users table.

### Determine the length of admin's password

giving length as 15 error message recived so the condition is true

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ae9d5c46-7470-43d7-be1f-008c017f601f)

giving length as 25 error message is not recived so condition is false, so the password range is between 15~25

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d9c4be96-17c8-4df0-affd-699941dfadd5)

To find the length of the password send qury to  Intruder then and Add the password length part as payload and select attack type as SNIPER.
Then go to  payload sleect payload type as numbers after that set from 1 to 25 and start the attack 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/adbc7c01-5ded-4a89-b071-5f851d6dc01d)

the result has error till 19 so 20 is the exact length of the password.

### Finding the 20 characters length password by Brute force

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/fc12686a-4b84-4689-a142-322f037ce99c)

`'||(SELECT CASE WHEN SUBSTR(password,1,1)='a' THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'`

a is not the first letter of the password.

To find the first character of the password send qury to  Intruder then and Add the string part as payload and select attack type as Cluster Bomb .
Then go to  payload sleect payload type as bruteforce set min and max =1  and start the attack 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e0865691-c5ac-459f-a358-3489a5f46c66)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/36b84ad7-ddcf-4176-868a-bcb50d5b548f)

the password is got as `furqyd5eyu1ij9awrgq8`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b7d2a169-4adb-495b-816f-ca74cf71b3f4)

Logged in as administrator, solved the lab successfully


