Create IAM role first 
This role will allow us to send metric to cloudwatch
Use Server Policy not admin

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/500b3bec-d961-456f-aa02-c8323e6ec77b)


![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9ee8bcfd-d605-48e5-acb0-32a9907bf75f)


Add role name
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/34d66186-a328-4463-94dd-92e6be3546db)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/92392dba-65a8-4e85-a095-9ddf3a90b82c)


Create test ec2 instance to leverage this role 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6441fcbe-941b-43fc-83ee-3684c28815ed)


Firewall rule
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3b69c89c-2afd-4cd4-93b7-0492a74a30f0)


Launch instance
Connect using instance connect for logging
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5c5732d9-5b14-47bb-8509-51cad45a47bb)


Install webserver 
Webserver to get log from http 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5b1074d8-35f7-4882-a3cb-93c83e0b0159)


Test html 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ff805c99-f726-4285-bac8-f4aa4fecc2f9)


Start httpd server
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b34a6b48-fa6c-470e-9f8f-881a8e703ff3)


Enable to survive restart
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a69f9a80-e532-4387-b780-161312d734f1)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b270870f-b6cd-4065-bc4e-34ce799b6726)




Our request log 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/362fb5a2-faf1-4e63-966f-f53382b59abf)


Get error log
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b3876b17-aae5-41ba-ba0c-2c1393b25e2a)


These are example log we want to send to cloudwatch unified agent 

Install cloudwatchagent
sudo yum install amazon-cloudwatch-agent 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ac2da36c-1eef-41fc-8a12-c77188acfa05)



Run wizard to configure cloudwatch agent
sudo /opt/aws/amazon-cloudwatch-agent/amazon-cloudwatch-agent-config-wizard
 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1e40198f-4bfa-4b13-917b-f432dcfb9151)


![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/968f3850-dfaf-4d13-ad06-006658fc3076)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d5eead14-f2b2-4364-b98f-689e6b45091b)


Collectd we don’t have install so it will fail to start
Reply no

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/21235281-ac39-4f16-9a12-9f6e6a98600a)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3512bcde-b35d-42db-8286-74ffd8610abb)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6d0e96fd-67f0-4d14-a30a-8d464425b810)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e3c62c8d-6c13-4fed-ac28-6a019b10f5c8)






Log retention
Add any additional log file to monitor
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6dd65744-4817-4c73-b029-cea06e2b4361)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f95cdf1c-5aa2-426e-955a-9bf939fe145c)

Parameter store wont work unless we have correct permission 

Attach iam role to instance
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c04cbc97-c256-4071-bc26-fe4cdc4e5c48)



Attach policies
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/350c3dee-b593-4991-8e76-b9cc651fb8c7)


Attach admin policies to put parameter into ssm store
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bd88ab8f-702d-4a54-8bee-ba4ac205d8e6)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f5cf3b6e-e600-41d9-bed6-9f02164ce51f)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5b355367-768f-46e9-8945-562aac039cd2)


Completed
Now go to ssm parameter store we have our parameter
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/86938614-c276-4ddf-aafe-12b401d81243)


If you want to boot up to this parameter assume this a whole new instance
Boot up from this configuration from parameter store to install configuration to parameter store 

Fetch config two option
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0e6482df-c729-4df3-9203-d8731b813f79)


Succeeded 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/04640456-876b-4797-b3f6-e603070b2755)


Now have log
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/06e4e758-79c4-4639-bd56-678922beaed9)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a084fa3c-041a-4c85-bd82-e7b49286cf91)






Metrics 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b6d13b03-d4c6-4aba-b7e1-7d3c656e3f63)

