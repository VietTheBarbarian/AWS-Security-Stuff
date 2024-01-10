Default event bus
Created by default in your account and start defining rule on it 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0f94f8dc-10a0-4de0-9ad7-34938dab1079)



You can create your own event bus 
You can Archive if you want to in case you want to debug and also do automated scheme discovery 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fbab81ee-86db-4850-a4e0-b946a36da27a)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/55030b64-5a16-4a4c-a30c-af6b96e66119)




Click create
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4ae155ab-b051-417c-98f7-8d463f0e5c15)



Event partners
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8235f2eb-fd3b-47fd-be44-3a81e0aa8092)


If we want event from auth0 
Follow instruction
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/01f4dcf0-9cfd-49b8-bfbd-5dd6e8238c31)



We need to create some rule for our event bus
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/cba5cddd-78f6-4efa-8c60-77f32fa8a5fb)


Our rule for default bus
Schedule use cron 
Rule with an event pattern 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/cf11c9d9-0983-4023-8ed9-46be01926c31)




Choose an event source
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/cf4db33a-cf71-4525-bfd7-eb55deb2bb6b)

 
Next we can filter with sample event
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/802751e6-efb3-4a80-900c-d6b9fe7094b8)


We can test with sandbox
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/20f0fabd-a827-4b0d-ad39-0aa940b6d1b6)


Than test against our event pattern
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/56dd0a67-841f-44fb-b5fe-96ef88c87f0f)




Our sample event
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bcba2a14-1ee5-404c-98df-9ae122532906)



If we want to see if your instance been stopped
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1bfb5728-7904-453e-a70a-7f9f62f5b584)


Crate an event pattern
Choose instance state change notification
Sample event match
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/df4f8036-069e-408f-a6ab-978616ffb16e)




If we changed to running state our event wont be caught
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b422b34b-5165-44d4-8aaa-5c0be3b4db93)


Select target to be notifed or centralized 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4fce2ffa-680a-4507-82f0-d2d9b7378c5d)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/edb4804e-50d6-400e-b106-a1ab9e161227)






Sns to get notifed 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/13ef3032-5ed4-4e00-9fb1-46f8a2f6bf4e)



Let create and try it out
Terminate your instance and make sure your sns is registered with your email 



Schema registry
Look at scheme of event
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9e1572da-44c5-413f-8781-0649bbec6f90)





Instead of writing manual code you can use the code binding
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ab8e8759-4188-4333-b4cc-ebc5b1111533)



