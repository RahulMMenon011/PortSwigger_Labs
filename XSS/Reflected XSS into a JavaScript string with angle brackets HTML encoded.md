![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/752358aa-edb9-4645-b1c2-0316959e3a59)

### Solution

Searching for a string, we are able to identify that the string is present inside the script tag 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e157fda5-bd26-4526-aa73-873182a36abf)

we have to break out of that tag inorder to generate the alert

payload used is 
```js
''-alert(1)-''
```
![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/82e62acd-9480-4355-9e43-430d1dd21649)

lab solved

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e3925edb-15e0-47a6-a0fc-167c4633db0a)
