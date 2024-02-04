This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables. The first step of such an attack is to determine the number of columns that are being returned by the query. 

To solve the lab, determine the number of columns returned by the query by performing a SQL injection UNION attack that returns an additional row containing null values.

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/4919d2f4-cb38-4406-81a3-60448db7a6d8)


Using Burp Suite to intercept and modify the request that sets the product category filter.

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/22230d5e-71a3-4e30-b0f4-71d7045f3c1a)

Initialy gave the payload `+UNION+SELECT+NULL,NULL--`

we got the internal error

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/e3afe77e-90c5-4a12-8a1c-249819df6ee8)

now modified the payload to `'+UNION+SELECT+NULL,NULL,NULL--` 

Only after giving three NULL values the error dissapeared,so the number of columns that are being returned by the query is 3.
