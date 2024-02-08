to detect drift we can use cloudformation drift
portect against manual configuration changes 

Example:
Setup cloudformation stack to create two security group 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/107b302e-fe7d-45f7-811d-fd722b460378)

Change manualy the security group configuration
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f1ce8bab-8323-46a3-ad59-69235773e201)

Changing inbound rule of our security group.
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6343b8fc-3039-4992-b578-9f64814cfe7f)

let delete the other security group.
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/20086963-0c02-4e33-a0dc-86394f89eab6)

To make our stack aware that a drift occur go to stack action and detect drift 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ec886cc1-3434-44c3-9921-98d8bf8dfdf0)

Drift result
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b4e84a64-0ae0-451b-85cf-c354938dfb3a)

view drift details
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/aec70ac4-dc14-4a8d-9b85-95e67f5e44ff)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/18fae75c-e48a-400b-86b3-f8860201dbd9)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9d243213-2cf8-4393-811c-53baa83117c3)
