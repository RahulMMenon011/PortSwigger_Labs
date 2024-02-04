This lab contains a SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables. To construct such an attack, you first need to determine the number of columns returned by the query. You can do this using a technique you learned in a previous lab. The next step is to identify a column that is compatible with string data.

The lab will provide a random value that you need to make appear within the query results. To solve the lab, perform a SQL injection UNION attack that returns an additional row containing the value provided. This technique helps you determine which columns are compatible with string data.

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/7edd65f0-0a5c-4bab-99c3-e66036c3111a)

* Using Burp Suite we intercept and modify the request that sets the product category filter.
* Determine the number of columns that are being returned by the query. 
* Verify that the query is returning three columns, using the following payload in the category parameter

`'+UNION+SELECT+NULL,NULL,NULL--`

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/7222a9d2-2bb5-4446-b4f6-bf3cd2c6ee90)

We didnt get any error so the query is returning three columns.

Now we will try retriving the string given in the lab `qb4D4l`

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/ad89e72c-8e65-4e7d-aa04-86a804b95767)

By replacing the second NULL with the given string we were able to retrive the given string, so the second column contains the text here.
