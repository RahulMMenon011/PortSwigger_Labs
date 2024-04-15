![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/78871727-1c71-4462-9e8e-3784293d0c55)

### Solution

we will give a comment in the blog

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/328b1ddc-838c-41d8-a906-280be9dc67e5)

 the random string has been reflected inside an onclick event handler attribute.

 ![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e415d8fe-d95b-47c0-bd9b-4c938621bcc4)

>This is where the vulnerability comes into play. It takes href value as an input from the user, then passes this input directly into the tracker function without proper input sanitization.

Try to inject another input to the Website input field. But this time make sure you use single quotes in your input, then observe that single quotes has been escaped by backslash.

```js
'abcd
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e5296fab-74ed-4799-bcf6-729f5afd8b68)

we can see that the `'` was escaped by backslash character

so the payload that we will use is 

```js
&apos;-alert()-&apos;
```

Clicking the name above your comment should trigger an alert.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ee2a8d2c-b1e3-4081-8b3c-279d4ec75330)

clicking the name gives a pop up

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/55a7601e-645b-4a60-99d6-5a98c03a938a)

the html code

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/00234073-41c1-4e77-909b-3a4c83839ab4)

lab solved succesfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/fe0fa508-d85f-4154-aa43-6760d6ca14dd)
