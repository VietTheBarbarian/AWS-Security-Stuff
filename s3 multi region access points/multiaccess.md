Failover and multi region access point

Create two s3 buckets
Two bucket in two different region
I want to have two buckets in two different regions
that will hold the same data and it will be served
by the same multi-region access point.
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/17404093-01a4-4598-99b8-b29d81d319c8)

Go to multi region access point and create one
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4ac967c6-28f5-422f-954e-0c858b5f8fde)

Give it a name than add bucket 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7c9ea1d9-875f-483b-968c-71c01c2af7ad)

Add the two bucket we created. Should be from two different region 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ecc289f3-293d-4f88-90d2-c17e7f83ca33)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ff5aa746-c35a-4f08-b9f8-c0290e3ae2f3)

Block all public access and create
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3ca206c3-d152-4ce9-aee4-85f329bdd6f8)

Take a long time to create
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/af356dbf-2862-4dbf-887f-9a3df5bff818)

When ready here all its properties 
arn 
alias etc
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/28015490-f119-4950-a566-2a0082ecfbf6)

Need to define a access point policy 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2f0b995c-e980-4aff-ae2a-940a3f3ea289)

And also replication and failover
we get a map here to what we want for more visual 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/763607f4-dad9-4854-80e3-41d04339f24d)

Create replication rule 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/30e19b57-f717-40c9-bcb9-b75a0a529e50)

Choose simpliest is first one 
high availability and failover
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/53f383af-ef93-49dc-a4d1-5610b4416205)

To enable this we need to run on failover
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5cdcb7ac-f3b0-4724-827f-d8023e8f6681)

Enable replication rule name
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e777f21e-31f0-49ba-a651-10323d683174)

Apply replication rule scope tpo all the objecsts in the bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c98ca6b3-8b47-4ddf-8c01-960af7f3f9b7)

Create
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/10eaede6-7dde-40fb-9aad-c02f5a493980)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8cc641be-bba9-477b-a1d6-6beaf4d44da0)

Go back to our map and we can see two way replication for our bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ccd3877e-832b-4bef-88ee-979a0fd03d4c)

Can also be verify in our replication rules on our s3 bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ac13af5f-c3e2-4693-a869-d798ca2a92d5)
