s3 access point 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fdfac355-488f-437e-bb0f-9f1f27dd45c8)

Give it a access point name
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2b3099c4-cc31-40c7-a403-6bddb27c633e)

Specify bucket name 
Region is determined by your bucket location
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a6a8f0b6-5535-411e-bdaf-daee3a0ce6e9)

Network origin
is this vpc access? or internet acess?
Will use internet for this demo ad block all public access
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/845bd414-2ba1-4183-a05c-aaca833a7abf)

Access point policy
https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-points-policies.html
Go to policy examples 
Allow us to write to thie directory 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/810343f1-dc2d-46ea-a405-603515096ecb)

Create
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/76eefda2-7158-4511-a7e8-0f7d5beb6bef)

We can go to bucket permission and we need to change the bucket policy 
Blocking any access other than access point 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/42b9fa58-dbc8-4f00-aa85-d1fd6e266367)

Paste bucket policy in 
Only access bucket from this access point 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8f0fd962-db13-47b7-843d-4a91c101c14c)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1ceca4b9-dde8-42eb-a442-889b0fe871ed)
