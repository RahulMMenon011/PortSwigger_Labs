![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/1b4eebf7-e26b-41c8-a7cd-e60ee6fd8ca7)![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/35d2fb8f-1693-4139-87f9-d54bf8e7b8d3)

### Solution

Inject a standard XSS Payload.

```js
<img src=1 onerror=alert()>
```
![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/39916cb5-cddf-43a8-813b-7a895be4bc7e)

Error recived

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d148f00b-9615-43ca-8a55-59cbb81b5bea)

This implies that the filtering is done and blocking our request.

but we could see that the angle brackets `<>` were not being filtered

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/2d3c19da-c885-47cc-be2a-7e223daeae89)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8f183e7f-e0f6-46b6-b726-c0a6c49c533c)

no error here

>To find the Payload first we need to find the tags and attributes which will bypass this WAF.For that we'll use use Burp Intruder to test which tags and attributes are not being blocked by WAF.

Capture the request

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8e416e91-1d50-4b5d-8d56-9352e38c2bdc)

send to intruder.In Burp Intruder, in the Positions tab, replace the value of the search term with: <>.Place the cursor between the angle brackets and click "Add §" twice, to create a payload position. The value of the search term should now look like: <§§>

Now Visit the XSS cheat sheet and click "Copy tags to clipboard".

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e6687082-4cd2-4023-9023-6998008a1d9e)

In Burp Intruder, in the Payloads tab, click "Paste" to paste the list of tags into the payloads list. Click "Start attack".

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8fd1c4dd-a65a-4489-b0af-c2f8bf057f47)

When the attack is finished, review the results. Note that all payloads caused an HTTP 400 response, except for the body payload, which caused a 200 response.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/48cf19d6-c2b1-4a8e-88cf-3bece4f115f9)

now send the `<body>` tag to the search box

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/3ab2c42f-78ef-4643-bcc5-14d13d1380de)

it was succesful

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f2ed72cb-e831-4287-ae03-4987cb7f9891)

>Now we need find the attributes which will bypass this WAF.For send this request Intruder replace your search term with <body%20=1> .Place the cursor before the = character and click "Add §" twice, to create a payload position. The value of the search term should now look like: <body%20§§=1>

Visit the XSS cheat sheet and click "copy events to clipboard".

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/4aa8bed8-2253-4bc6-8bc8-eed6adcfef29)

In Burp Intruder, in the Payloads tab, click "Clear" to remove the previous payloads. Then click "Paste" to paste the list of attributes into the payloads list. Click "Start attack".

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/524641fd-f041-400f-aeb7-8855b853bad2)

the result

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/2432c12c-b2d6-474d-939c-331c8ec7071d)

Your solution must not require any user interaction. Manually causing print() to be called in your own browser will not solve the lab.
All the Payloads events which give response of 200 has require user interaction.

we are taking the event onbeforeinput.

### Payload

```js
<body onbeforeinput= alert()>
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/38bdf900-81c0-4cb7-987c-91955f9c7a59)

result

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/9e2ee2f2-e2f0-4db2-80bb-2745784c59ca)

If we need to get the alert pop we need type something in search blog that will be user interaction.

When i tried to type the pop alert came.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/78b397c2-fc8a-473e-8a68-6163ab4038ea)

we need to Manually causing `print()` to be called in your own browser will not solve the lab.Similarly `onresize` event.

### Payload

```js
<body onresize= print()>
```
result

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/99ba7c7d-431f-4cbf-bbf2-4052a024fc3d)

If we need to get the print we need press the minmise button.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/9291c437-832e-4dba-b50c-cfa2cf6327ac)

So the every Payloads events are has user interaction . For that we can use iframe and onresize with that because iframe has a property to cahnge its size so that why this will work with iframe.

### Payload

```js
<iframe src = "exploit url path "onload=this.style.width="pixel size according to you.px"></iframe>
```
First this i frame will load the sorce exploit url initally .Once it completely loads right this onloadget triger automatically which will ultimately change this.style.width="pixel size according to you.px" the width of the iframe. when width change the malicious payload will get executed .






