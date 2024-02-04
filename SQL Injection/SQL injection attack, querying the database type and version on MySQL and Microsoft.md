This lab contains a SQL injection vulnerability in the product category filter. You can use a UNION attack to retrieve the results from an injected query.

To solve the lab, display the database version string.

First we need to check how many columns are there

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/3a9ee582-70da-45f3-a2a2-a84ac7a46db8)

Now we check which of the columns returns the text value using payload `UNION+SELECT+'a','b'#

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/1ed360db-2ccc-4556-a850-6547c4b8eecd)

Finally used the payload `UNION+SELECT+NULL,@@version#` to retrive the version

![image](https://github.com/RahulMMenon011/Web_Security/assets/140642506/d09cd110-a88f-46ad-b5b1-8bd628e36412)

