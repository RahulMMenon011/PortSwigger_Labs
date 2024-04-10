![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/df6115e6-7cf9-4ea6-a782-6dc1add4b222)

### Solution

Searching a random string and later inspecting the element we can see that it is inside a quoted attribute

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/9a010422-eca7-4b29-8226-dc573a10b952)

 We will input the following payload to escape the quoted attribute 

 ```js
 "onmouseover="alert(1)
 ```
Successfully called the alert

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/279b7851-8b94-4fbe-b66d-f9ff90a5521b)

Lab completed.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/66b633d7-fd84-46e5-b762-5d118fc30411)
