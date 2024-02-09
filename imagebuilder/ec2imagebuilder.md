Create a image pipeline 
Option to create a build schedule 
Cron expression
And 
Manual 
Doing manual 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/eefff78b-e742-48c6-86ef-1062c164fdfe)

Choose a recipe
How source image is going to be customized 
Create new recipe 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a50cbd8d-7841-444a-8465-fb63c2825cbc)

AMI image
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e3311ff1-570b-4ec8-9196-f27ceba90041)

Source image 
Can select managed images or something from SSM 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1105fd9b-cf7b-48b2-8376-3cb60abe6e00)

Image origin
Quick start from amazon-managed
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/69096049-4523-42ca-a618-e56dc7e50ab7)

Components 
How we want to customize our image 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fc71578e-bfc1-44b6-ae91-6989a707c66a)

Java on our ami
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f1760525-9f3f-4dd3-a292-c075bc580400)

Next let install aws-cli verison 2 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c82d99fa-7fe0-4cd0-9dd0-f874bebcc1fc)

two component we can reorder installed
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4dfe959f-7e56-4d91-8ae7-c14ffe311237)

Test for ami working. Skipped
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/97d1cafc-75e4-4cf2-8786-13e1d6dd7909)

Define what type of instance you want
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/01903b01-15ce-48af-adcb-736756032fb4)

Create a new infrastructure configuration 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/032102ed-cd29-435e-9e5b-dc5c8ac71ef4)

Create new role
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bbe3da47-2b26-47c8-b959-467f18350ac3)

Roles for ec2 instances
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c884a6cb-853b-4df9-8e5c-b1ef0933bd84)

If we go back to configuration options and select the following it will give you the type of role you need 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4008e3c4-67ed-42af-9673-62d4ef94bbe5)

Back to role 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8e62f5cf-a812-4db7-bb9f-7f5f5d72d277)

Grab that ROLE  
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/095fd601-10de-40c9-a108-a9afbe6265b5)

Instance type and SNS notifcation if you want 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ae974467-27ec-4628-a11e-8ec566de19ae)

Define distrobution setting 
Useful for region distrobution 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/66bcbd98-eec8-4fb9-9e3b-a64a10663f9a)

Create that pipeline
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/13f61416-d28b-4244-9a33-22814e1b37e8)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c34c65a8-5a05-4ea9-9abd-6f3f0aa337f9)

Run the pipeline
Now wait
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/af7ff535-a505-4140-b66a-c3fc666201f7)

 After 30 minute we got our instance 
 ![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bccd2631-7438-4bd2-bc38-8a51d1ea0018)

We can go to tag and see that it created by ec2 image builder 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8ee1fe2d-f178-496d-9187-6df214f1edc8)

Waiting some more we will see we are on testing 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/71e67602-30e7-4a91-b54a-ed1c0710b69e)

look at what happening at testing 
terminate cause we build it our test instance is running 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/eb0246c9-3924-400b-9906-041a5bd3ed9f)

Our ami 
test instance being launch from this ami 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3f32373b-eac3-4441-b700-fc7cdb7f91ec)

last stage distribution
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/94e53054-639f-4966-9792-66eca3db2a71)

only one region tho is this will be fast
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a84d9d71-9ab5-472e-9d8f-5a211a2458b6)

Available now
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1029f0a3-502d-4f42-8500-df046f5b7809)

Now launch the instance using ec2 image builder 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6a117701-caeb-4b46-baaa-5461a863bf9c)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d842dc31-9f5d-4d62-905b-ef8055577288)

see if our java is install 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/11738023-cc46-47a0-b7cb-d60abccba738)
