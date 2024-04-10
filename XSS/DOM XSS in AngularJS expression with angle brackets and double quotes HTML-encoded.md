![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/af2f3ccd-3bc8-4b30-bbeb-3cf77f0eb6d5)

### Solution

AngularJS expressions are executed in HTML sections inside of nodes containing the `ng-app` attribute

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/266a0b13-2b9a-4586-8c5b-db21bd7e7b61)

We could see that the search box is enclosed in the `ng-app` attribute

We are checking the execution of expression using command `foobar{{1+2}}`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7a335a2f-7338-47ba-9abc-3e3f205dbcc0)

Now we can use the payload to show an alert  
```js
{{$on.constructor('alert(1)')()}}
```
![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7651f69c-7662-4643-bdc9-2e7686f01c8f)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b67d3d4b-de03-431a-915f-b34fbf1f1a5a)

Alertbox raised, lab solved
