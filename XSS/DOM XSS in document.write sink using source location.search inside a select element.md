![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f790df1e-5886-4221-b42c-900e98dc8dba)

### Solution

On the product pages, notice that the we can see that JavaScript extracts a storeId parameter from the location.search source. It then uses document.write to create a new option in the select element for the stock checker functionality.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0dbc7073-ea7d-4955-b24a-ba8bfc51d737)

Added a random string in the URL and now it is shown in the product request option 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e688810c-3763-42a6-a1d4-ac0ccd97a83d)

Modifying the URL to get out of the select tag and printing an alert statement.

the payload `"</select><img src=1 onerror=alert(1)` is used

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/4654d578-dc80-46ae-91d9-3d3d184c21f5)

Lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/74772be7-6c02-41cb-8510-8f85b990cc3b)
