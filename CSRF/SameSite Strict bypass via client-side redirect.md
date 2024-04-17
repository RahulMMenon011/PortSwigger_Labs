![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/23e178a2-4d9b-438e-99a2-1c8874987be1)

### Solution

the POST /my-account/change-email request and notice that this doesn't contain any unpredictable tokens, so may be vulnerable to CSRF if you can bypass any SameSite cookie restrictions.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/899044fa-2cf7-41ae-850e-a519645cbd38)

Look at the response to your POST /login request. Notice that the website explicitly specifies SameSite=Strict when setting session cookies. This prevents the browser from including these cookies in cross-site requests.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/501bdc6b-5fac-411f-b443-871dfbb2a55c)

### Identify a suitable gadget

In the browser, go to one of the blog posts and post an arbitrary comment. Observe that you're initially sent to a confirmation page at `/post/comment/confirmation?postId=x` but, after a few seconds, you're taken back to the blog post.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d6677504-2d79-4471-b095-67f1a663ab4d)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ceeb8fbe-1031-45a6-af4e-7a4f6c334c56)

In the proxy history, right-click on the GET /post/comment/confirmation?postId=7 request and select Copy URL.And Try injecting a path traversal sequence so that the dynamically constructed redirect URL will point to your account page:

```js
/post/comment/confirmation?postId=7/../../my-account
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/649132fa-80db-48d6-9a85-39fd22b7dcb3)

Observe that the browser normalizes this URL and successfully takes you to your account page. This confirms that you can use the postId parameter to elicit a GET request for an arbitrary endpoint on the target site.

### Bypass the SameSite restrictions

In the browser, go to the exploit server and create a script that induces the viewer's browser to send the GET request you just tested. The following is one possible approach

```js
<script>
    document.location = "https://YOUR-LAB-ID.web-security-academy.net/post/comment/confirmation?postId=../my-account";
</script>
```

stored and view the exploit

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/8d42946a-c27c-44fb-860e-353d9815d97d)

Observe that when the client-side redirect takes place, you still end up on your logged-in account page. This confirms that the browser included your authenticated session cookie in the second request, even though the initial comment-submission request was initiated from an arbitrary external site.

### Craft an exploit

In Burp Repeater POST /my-account/change-email request Change request method. Burp automatically generates an equivalent GET request.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/12cb213b-f764-4955-ae16-d3f7983b8653)

Go back to the exploit server and change the postId parameter in your exploit so that the redirect causes the browser to send the equivalent GET request for changing your email address:

```js
<script>
    document.location = "https://0abb00f204775ab3844f81c400d800d1.web-security-academy.net/post/comment/confirmation?postId=../my-account/change-email?email=abcd7%40gmail.com%26submit=1";
</script>
```

Deliver the exploit to the victim. After a few seconds, the lab is solved

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/9bb4b85c-0aea-4064-9973-16c017ea4465)
