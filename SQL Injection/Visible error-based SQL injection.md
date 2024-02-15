This lab contains a SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs a SQL query containing the value of the submitted cookie. The results of the SQL query are not returned.

The database contains a different table called users, with columns called username and password. To solve the lab, find a way to leak the password for the administrator user, then log in to their account.

### Solution

Captured the http get request using interceptor

after giving a `'` at the tracking id an error is formed

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a2e85268-cdb9-4109-b0eb-7e433876dbe6)

after giving `--` to comment out rest of the query we no longer recive an error, so the query is now valid

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/2c9acda3-6034-4247-9cbd-6e70c4d234b1)

now casting the returned value to an int data type,

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b944618c-787c-4c40-ab55-d24f8290a4cb)

after trying to cast, we are getting a new kind of error message.

after slightly modifying the cast query by adding `1=` value, now the error dissaperaers.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/bd007904-4714-49bc-9cb7-df394e8ff466)

now modifying the query to select usernames

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a8e697f3-de59-4b99-9322-11d30b611a82)

editing the query to remove the error

removed the original value of cookie to free up characters, now new error recived

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b9d58c3a-0a62-4f57-856e-378731d0bd3c)

now using the `Limit 1` value to limit the returned query to 1 row

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/29a9d37f-5dc5-404c-8e1b-3bd3438c78f4)

we understood that administrator is the 1st username in the table, now modifying the query.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d7bc5bb8-b995-4dab-8a31-2f6fd146e618)

got the password, logged in as administrator and completed the lab succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8dbd23f9-6e82-4735-8f97-e42bcc5fde26)






