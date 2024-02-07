AWS config
Not free more resources you record the more you pay 
Include global resources
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/491a50f3-ccce-4715-8996-bd48dedf2404)

To record all the resources configuration we need to create a config service-linked role 
Will be stored on a s3 bucket 
We can also have SNS topic stream
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7a70d0e7-cb54-4fd1-bf0d-79322baa1a04)

Lots of managed rules to choose from 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/19471b01-1681-4359-97ed-2f418efe23b6)

Review
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/16bb2f99-dfb5-4cb8-a691-9bf7506cad48)

Resource that discovered might take a while
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1fe5fcf4-fe8c-49e1-9136-5a611bdc4886)

Getting timeline on resources
Found on cloudtrail
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a2196fda-a8c0-41fa-be8b-3cfcbf4bbfc0)

Adding a compliance rule 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d49f39a1-3055-4233-bc17-285706305481)

Triggered based on resource that change and specify ec2 instance  
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/00e708f0-da45-450d-8ea9-985e89e190f2)

Specify your amiids parameters
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1b8b5476-5833-43a4-8ec5-cd0221e43fea)

Managed rule for ssh 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/39f75a0e-1dfa-49e8-bf10-ea6582389836)

Looking at our result 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/236d1eb7-65c4-4402-b397-cef93a7e840b)

Filter by all resources
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f986665d-48c1-4d00-9436-eb9575eb61eb)

One simple change can lead to compliant
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ad88eaad-908d-4ee4-a7b2-4e5de9e1b9c8)

We can also add manual or automatic remediation for any managed rule issue to get resolve
Choose manual and this will do SSM on that resources for the managed rule triggered 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/654d534f-b657-4768-afc6-80f7b58bc079)

