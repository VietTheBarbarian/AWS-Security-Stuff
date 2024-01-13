DNS resolution hand on
Right click on vpc and edit DNS hostnames
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a53d1a0f-79da-4ec8-96a9-4a04edb2feb8)

enable dns hostnames
Indicates whether instances with public ip addresses get corresponding public DNS hostnames 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/78bceecc-2260-4ec7-a0fd-921cedfbc121)

If we go to our ec2 instances and look at our details 
Look at our bastion host
we can see that we have a public IPV4 addresses but not a public ipv4 DNS 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/99796d14-08d4-4ea9-99c7-5db17b3be20d)

Go back and Click enable DNS hostnames and save changes
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/66171dd8-0ff5-4ff8-b422-21c2321bc8e6)

So now if we go to our ec2 instance we can see a public ipv4 dns address which will resolve to your public ipv4 address
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3cd044ab-68bd-48c1-81e8-df1164c1b7e5)

We can also look at edit DNS resolution 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ec756cda-74c5-4c62-99ef-59eff7d3bb9d)

As you can see DNS resolution is already enabled by default 
That mean our instance will resolve dns name to aws
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/13c11dd1-ee25-4ddf-a4af-ba840f33a5d9)

Next step look at route 53 hosted zone
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fefc454c-bec9-49f0-80a0-d3b7285871d4)

Create a private one
Go to hosted zone
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c46fa210-c168-4cc5-80c9-befaaeeb671c)

Create hosted zone 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a9b21c38-51b6-4ad4-b4d2-395db78a7a9f)

Give it a name
Domain name that I done own but because it a private hosted zone it will allow it
will allow ec2 instance to resolve it
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5e66074d-14da-426f-b7ad-352172fa5c7a)

Select private hosted zone
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/46919b82-4b0c-487a-a5d0-a2831e5a6556)

Since it a private hosted zone you need to associate it with a specific vpc
Note: For each vpc that you associatate with a private hosted zone, you must set the amazon vpc settings enableDnsHostnames and enableDnsSupport to true
We did this previously 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9887bfee-d6b6-4a71-be94-7721ea838b27)

Create hosted zone will cost 50 cents per month
Create this
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/67ded6f9-c92b-44ee-b04d-c8eb78cf51b4)

Our records
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a13670a4-4829-4548-9fb3-e5d637a44568)

lets create a new record
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/86cd04a3-e0b1-423e-856c-1ad39cae4975)

This one is going to be a cname to google.com
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/88545326-a79e-4700-a83d-5d6d4df573dc)

Create this record
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5571908d-bdf4-4417-9a60-c517f7a49519)

Our instance in the vpc can reolve this hostname 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5462d011-1aa7-48d4-b5cb-bb350d3e97bf)

Connect to your bastion host do the dig to test
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9170e202-9d67-4319-a63e-a66da284fd20)

We are now able to create internal private records for our dns 
Let us create interesting domain names for our internal applications 


