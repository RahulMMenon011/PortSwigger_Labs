This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs a SQL query containing the value of the submitted cookie.

The results of the SQL query are not returned, and no error messages are displayed. But the application includes a "Welcome back" message in the page if the query returns any rows.

The database contains a different table called users, with columns called username and password. You need to exploit the blind SQL injection vulnerability to find out the password of the administrator user.

To solve the lab, log in as the administrator user.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/3894143f-5ed1-4e5f-acc5-db228923003f)

Captured the webpage in burpsuite, if conditions are true the `Welcome back!` message will be shown.

A payload `' AND '1'='1`  is given in the cookie section, we got `Welcome back!` message so the condition is true.

![Screenshot 2024-02-05 221938](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d11f60bc-a4d0-473c-bc23-9f8116d8cd6f)

When the payload `' AND '1'='2` was given the `Welcome back!` message dissapeared because the condition is false

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/3d690563-7caa-4482-a441-78afeadc13b0)

### Checking if the table called users is present

We gave the payload `' AND (SELECT 'abc' FROM users LIMIT 1)='abc`  and `Welcome back!` is show in response page so the condition is true.

From this we can verify that there exists a table called users

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/283ce632-03d4-492f-902f-94c214fcf7df)

### Checking if administrator is present in the users table

Using the `' AND (SELECT 'abc' FROM users WHERE username='administrator')='abc` payload we can verify there is a username called administrator in the users table due to the presence of `Welcome back!` message.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/56dab273-1f24-434d-91c1-6234b6519832)

### Checking the length of the password

Tried assigning a length of `15`, Welcome back message is present so it is true

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b39266ca-2d98-4f7f-a4fa-9c9d3289049a)

Tried assigninf a length of `25`, the Welcome back message dissapeared so the password is in the range 15 ~ 25

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f797baca-b7f2-46f0-9ff9-b8b9342e8f38)

### Determining the exact length of password

We use the sniper attack available on burpsuite

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6e0cb31d-6dd7-4895-8b26-e862d3f25379)

Edited the payload and settings for our attack

set the range form 1 to 25

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/07561ca6-8889-49b6-ac8b-68a900b1e29d)

The expression  Welcome will be checked each time

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/90cbacd8-daff-4d15-aeb3-68ec3e77c364)

In the result the Welcome message was show up until 19 length, so our password contains 20 length

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d7d17582-cc3a-4325-81aa-b4a94919111d)

### Determining the first letter of our password

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b8917b46-bb76-4edf-83f4-ac9ebe7d2a1d)

The welcome message was not present so we understood the first letter is not `a` 

now using the sniper attack, the first letter is found to be `6`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/c8d5bd46-6071-493f-826a-9f892a53bdfc)

Now using cluster bomb to find complete password

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/3fd13c58-93da-4eab-999c-fec407fb7af1)

The password is got from the results

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f2a01b63-4cea-43de-ab83-c93b3691e818)

The password is `6lsu2w4mxdq25o3a3f79`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e98334cb-7b07-4e27-a942-5c6e948a0f2e)

Logged in as administrator successfully












