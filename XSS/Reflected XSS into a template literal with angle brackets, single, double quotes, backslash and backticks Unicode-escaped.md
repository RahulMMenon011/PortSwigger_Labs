![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/699f0b3e-0c4d-48f5-9629-0dadead5059b)

### Solution

First we enter a string in the search box 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/1609a2e2-8d4e-4eb2-a514-a0778fb7513e)

when we inspect the page we can see that it is inside the string tag

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ae07933e-6626-46c9-a011-c901b4ea2627)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6c1cc974-36fb-4854-96c1-d4e8df1f5255)

now we will use the payload

```js
${alert()}
```

when searched for the payloa dna alert poped up

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f8478cf2-e1cd-4586-8b55-507fb6637fd7)

html code

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/fd875fc2-79c6-4fef-bcc7-012f81dfe5fc)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/24ee918e-44d8-4c25-98f4-627d6caa5032)

lab solved succesfully
