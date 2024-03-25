![Screenshot 2024-03-25 112837](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/e242b24e-dd9b-4082-82fc-22527ecd3e91)

### Solution

We want to inject an attribute that calls the alert function.

we add the payload `/?%27accesskey=%27x%27onclick=%27alert(1)` to the URL

![Screenshot 2024-03-25 113050](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/98dd2523-fc33-43bb-9789-5769e88dea66)

when the user press the key combination `ALT+SHIFT+X` the alert function will pop up with 

![Screenshot 2024-03-25 113112](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/b6146a68-d022-4ccd-a1af-cf5de79fee21)

Lab solved succesfully.
