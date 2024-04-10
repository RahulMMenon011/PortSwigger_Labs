![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/514b709b-d0a8-4f89-855c-5e6cb3272e45)

### Solution

Tried generating the alert box using the comment section

```js
<script>alert()</script>
```

![Screenshot 2024-04-10 175842](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/cd6873ab-5bdf-4da0-9272-617d8c8e42f4)

nothing happned here

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/5f8ad227-4e76-457a-a38d-ebf3841cd8a6)

![320127142-6c33610b-9962-4de7-bbea-8f4d01736804](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f28ff0ac-a8df-49a4-846a-2126822c7239)

We could see that the alert option is inside the `<p>` tag

we need come out of the `<p> script </p>`. for that we will use `<>`

The payload used here is 

```js
<><img src=1 onerror=alert()>
```

>In an attempt to prevent XSS, the website uses the JavaScript replace() function to encode angle brackets. However, when the first argument is a string, the function only replaces the first occurrence. We exploit this vulnerability by simply including an extra set of angle brackets at the beginning of the comment. These angle brackets will be encoded, but any subsequent angle brackets will be unaffected, enabling us to effectively bypass the filter and inject HTML.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/dfc49730-2d7c-4512-b03e-7203ff3eee4a)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/4964649e-7572-46ef-94cd-7eb5c8ff4e5b)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/829b0b7f-560f-49de-abc8-b88b2efb07d9)

Alert was generated and lab solved succesfully
