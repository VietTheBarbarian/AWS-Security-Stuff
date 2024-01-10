Hand on Cloudalarm
Creating an alarm if the cpu usage go up to 100 percent 
Create a test ec2 instance 
Test should have no key pair and should not have any outbound or inbound
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5b97b482-1cf8-4bc0-b26f-3324ada7e655)


Create this alarm 
Select a metric 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/99a826bc-2bf2-4815-a5db-00b1f7eb3aff)


Choose a metric
This will be out instance ID(might take a while to appear due to propagation delay)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b4f50c45-5034-486e-a850-5e8de3b28a05)

Choose way to compute the metric(Statistic)


Period(period each metric get populated)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a4d2fdd3-aa43-4e17-ade9-7b56426a2cbe)


Conditions
3/3 datapoints to alarm so 15 minutes
>95 percent 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/637e2474-a1ec-45b8-bfba-15e5559ab2a3)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1a385d5c-60d6-4612-bf51-01c305c42323)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/39449782-427a-4310-a31f-e99c7c9f9bfd)




Configure actions for our conditions
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f6e559f0-477b-4b53-a1e9-929f665249fd)



Choose a ec2 action
 if you are in alarm than terminate this instance
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/dc12115a-482f-4a30-bd03-a93d32186f1a)


Give alarm name
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9639dc98-1334-4354-9405-d29322698042)



We created it
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8323a244-20a0-472e-b1e0-92e37a0649b9)


Test 
Set alarm state
https://docs.aws.amazon.com/cli/latest/reference/cloudwatch/set-alarm-state.html

Aws cloudwatch set-alarm-state --alarm-name (your alarm name) --state-value ALARM --state-reason testing
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7dab799f-5b18-4cb8-8856-0093aa38c89f)


Alarm state alerted
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/74567288-e9ec-4a4b-80ad-01d8680085f8)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/11a39731-2c78-4ddb-9543-482070722465)




