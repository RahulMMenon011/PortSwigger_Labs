![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/c92a33da-6193-43e8-acd2-2362b247028e)

### Solution

The term searched is inside `script` tag in html

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6db0392d-4148-4946-8ed2-01c41dd0d1c1)

tried searching `test'payload` and it could be seen that the `'` is changed to backslash,preventing us from breaking out of the string.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8d004181-6d73-456a-9a15-7a454265e5c6)

now we use the payload 

```js
</script><script>alert(1)</script>
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f22fc40b-8ee3-4402-b96d-0a6b87cc5fb4)

it triggered a popup

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/da7018f2-2514-44a9-812a-9a0bba2a9778)

lab solved succesfully
