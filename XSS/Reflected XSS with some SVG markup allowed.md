![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0bacc732-513b-476f-ad7e-c110c8ad91c4)

### Solution

Firstly inject a standard xss payload

```js
<img src=1 onerror=alert(1)>
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a83e32f0-4fd2-4e0b-bff2-29a1012fdbcb)

we got tag not allowed error.

now we check if svg tag is blocked

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6aab9e94-3714-4c0e-af02-ce38e51c4c3d)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/16752a14-1c03-4fc1-adfd-01b2bd91cc5e)

it is not blocking svg tag.

now we need to find a tag that can be used between svg tags

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/99280bee-90fa-4e18-a10a-d2fda489045f)

copied the tags from xss cheat sheet and used it as payload

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/504af2eb-937f-4cfe-8f7a-9b9780a5dccd)

the result

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7011fd32-cb8b-4359-8672-8d098384ce51)

so animatetransform tag can be used here

copying the events from xss cheatsheet to use as payload here

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/15115307-fb13-4ac0-a2c3-8786395bd4f2)

result

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/200eba1b-04ae-47b8-ac7a-410fd8613acb)

so we will be using onbegin tag

```js
<svg> <animatetransform onbegin="alert()"></animatetransform></svg>
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e7d3fcc6-b779-46c3-a16f-aceaa5e76b48)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/600026dc-351a-438d-b7c3-f9b45df2d085)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/42146a64-48cd-4200-8f49-83df25556d42)

lab is solved
