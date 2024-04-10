![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/91dc7a09-166f-4d2d-849d-de52074c73cb)


### Solution

Searching for the term `portswigger` in the website search box

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/4b8e3caa-8abd-4407-94d2-faf022f86706)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/14915ab3-54a7-49f9-86bd-e65c0d0005f0)

Notice that the string is reflected in a JSON response called search-results.

From the Site Map, open the searchResults.js file and notice that the JSON response is used with an eval() function call.

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/dca18251-c4cb-4178-b93a-e542cf4db8a9)

Send the request Repeter to experiment with it.

first tried broke out java string using \".The lab was shown outside the string.By commenting out the `}` we were able to break out

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/80d4734c-ff29-4ed5-8f00-796c2f65b921)

now the payload 
```js
\"-alert(1)}//
```
![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/569081a6-b6d6-4215-b1a9-4d4bfb53c245)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/53308f54-eaba-4096-b778-61d7f5e0d4ad)

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/f2c43b42-07b2-48c5-8357-424027e46c13)

alert recived and lab completed succesfully.
