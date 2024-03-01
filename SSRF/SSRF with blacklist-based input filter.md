![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6a4c84a2-540e-4cdb-853c-263c41c85e86)

### Solution

Used the check stock function and captured the http response through burp proxy

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/5829e698-ed34-4d38-9b9d-6a6c0a7a1b80)

Tried changing the StockAPI parameter to `http://127.0.0.1/admin` and sent request but it was blocked by the server

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/9b16f263-9c4f-4eb6-be7a-6bb340056259)

Changing the URL to `http://127.1` we got an http OK request

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/70ef98a1-826a-450b-b2c0-9d0d08ffec35)

adding the `/admin` the request was denied again

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/53b8702c-2201-4bb1-a45a-40dd6f85289e)

After doing double URL encoding on the character `a` by substituting `%2561` was able to bypass the block

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/49e2b766-9772-4b80-b5ce-4b8de5b0c85f)

Delelted user carlos and lab solved successfully

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/7bb243ac-dc77-44bd-ae49-cede774d83ba)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/86271df3-e2ed-4d94-bf01-fe7e9c1b8a96)
