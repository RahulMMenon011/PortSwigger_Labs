This lab contains a SQL injection vulnerability in its stock check feature. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables.

The database contains a users table, which contains the usernames and passwords of registered users. To solve the lab, perform a SQL injection attack to retrieve the admin user's credentials, then log in to their account.

### Solution

captured the stock checker POST request in burp and sent it to the repeater

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/4ba2bb40-1324-48cd-a508-9c3ce4f60efb)

Tried changing the store ID and it was evaluated succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/5bf1f2d9-dc0e-4bd2-9327-c54809bf50cd)

Tired the union command but the attack was detected

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a982267c-8a0e-48f6-ae3f-bbc93fe5a928)

Changed the payload to dec_entities 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/cf15784b-a4c8-424a-ae98-26d4e81ef008)

Bypassed the WAF succesfully, no error message was recived

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b5f8383a-0ab7-46bc-adeb-c54cb0153aab)

Fetched the username and password using the payload `username || '~' || password FROM users`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/c4f2a582-5042-478e-b934-8871cea41aef)

logged in as admin and solved lab succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/bd3961d1-2794-4367-bcdf-39f43ca75e50)



