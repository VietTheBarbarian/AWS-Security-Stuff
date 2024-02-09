Create a lambda function 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bd45af8f-b85e-4b5b-ba77-a831735b2de2)

We need a security group for our function for it to work in vpc 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bfd593a4-c852-4091-9de1-e73de99c42fb)

Attach our lambda function to a vpc 
Notice that the warning
We need to deploy on a private subnet with a nat for lambda function to have internet access 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/06bb14cf-3bb3-4b76-bccd-d03fef8f5c4d)

Give it the security group
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/20aa751b-1cf0-462c-a4d5-ac1d785d1730)

Save 
Error
We need to provide our lambda function more permission to do this operation believe it enimanagement
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/25a99bb3-f008-4882-bcab-ea75c23e9854)

Go to lambda function configuration 
click on role 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0d101ef9-de21-422b-8ac6-8fcf448bf7d4)

Attach policies to role
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5c7a2741-f2ac-436f-b93c-8b17be3ae5a9)

Attach 
ENIManagmeentPolicy to role 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1467e836-8af2-4093-9585-5f400af550c0)

Summary
Lambda function right to exist in vpc
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1de78790-c89c-41cd-ab0a-1ce9ba804ca3)
Take a while to update

Test succeed
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b7c43922-2440-4e88-8e64-b32e1f51f773)

More detail
We have eni created for this connection
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6143a19f-9563-4cbb-8559-a5ec2e90fb33)
