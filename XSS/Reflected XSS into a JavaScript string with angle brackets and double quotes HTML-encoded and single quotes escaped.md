![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d4895e19-ef50-40d4-8fb3-22f8ce333538)

### Solution

searched a term `security` in the box, the term is seen inside the `script` tag

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/a1581cce-eb76-44ed-8174-3126ba311f07)

tried sending `test'payload`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/ae22ce69-0270-411f-813a-3ec0e5507b1e)

the '`' was changed to backslash

tried sending `test\payload`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/3d4deb84-bd70-4e61-a3d3-37677e4ea4b8)

server added an additional backslash

After finding your string, you’ll see that the server responded with the addition of a backslash, ‘\’.

Since the title gave us a clue about the single quote, it is also giving us a clue by NOT mentioning the backslash. Maybe, if we successfully add our own backslash before our single quote, the server will insert it’s own backslash in between. Effectively, our backslash will escape the server’s backslash, leaving our single quote to terminate our search string.

now trying the payload `\'-alert(1)//`

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/31ed236c-367e-4e58-aa15-ad9c637e429a)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f7949a49-e45a-4626-9663-37ddcd31ba55)

lab solved succesfully
