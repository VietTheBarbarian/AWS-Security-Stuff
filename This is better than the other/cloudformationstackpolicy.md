Prevent accidental delete or update
Cloudformation stack to create ec2 instance and a dynamo db stable

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b7137618-dd02-4fad-acaf-c2472d22749a)


Our policy
Allow all update with a explicit deny to updadate:replace update:delete dynamodb table
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/67a51d41-27db-43c6-8802-32d6b8352bc3)

Create stack policy and attach our stack policy.json
Protect our stack update
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2df6cea9-e2dc-40b8-a8a2-37675244f9cb)

Created
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1caf5fba-5156-4844-a6fc-df0fbb2d130c)

Update our stack
instance type change and dynamo db table has more attributes
Will trigger a dynamo db table replacement 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/dda79a22-fe38-4922-b09c-3f8eff2b1bd8)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bf1fe43b-25b4-4fa5-83aa-0079a47fa157)

Update the stack
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7343fe4f-4af1-4e4d-9969-9d4ba86351a9)

Thanks to the stack policy our access will be deny to update stack policy 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/08a867a0-c332-4031-a10e-93ab00a760aa)
