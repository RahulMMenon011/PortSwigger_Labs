![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/cd739e00-8b79-48bb-b76a-44546d99dbd2)

###  Solution

The hashchange function is a vulnerable code

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/823871f7-a2f3-43bb-967d-2122a0d5779d)

By adding `#` along with the heading of text in the web page we can see that it automatically scrolls to that part

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/071884a7-7d5b-4684-9d05-04a288724a86)

So we can understand that anything after the # is being executed here.

creating an exploit `<iframe src="https://YOUR-LAB-ID.web-security-academy.net/#" onload="this.src+='<img src=x onerror=print()>'"></iframe>`

This will make the print() function appear

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/d8be7969-451d-4f65-9046-5d0ce64cf96e)

On the exploit server created and stored the exploit

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/c6e23b97-4638-430a-bba0-8067037a3d41)

After hitting the view exploit button the exploit called the `print()` fucntion, so we can be sure that the exploit works

now sending the exploit to the victim

![image](https://github.com/RahulMMenon011/PortSwigger_Labs/assets/140642506/6c7bbcd3-c3c3-454b-ac5d-6a2541e6818c)

exploit sent to the victim and lab solved
