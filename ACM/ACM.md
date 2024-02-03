option to provision private and private
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/48d21b18-8eac-42bc-9827-8893500e039b)

Will do public 
can import a cert if we already purchase one before
or 
request one (free)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/aae6d607-1c12-4664-bdaf-be0b81c53fb5)

give domain name
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/faab0647-c956-48f9-bcd7-b9e8ade3a0d9)

do dns validaiton to show that we do own that domain name 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2d3a7a6a-94cd-47f0-9a90-15579d4cf8f6)

need to ccreate a cname record for this to work
give us a direct link to route 53
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/651280be-bba6-4d59-a53f-179c5bab57c7)

Will create for us
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ea37a3c0-4df6-4df9-b011-df22dd719612)

take 30 minute for propogate 
pending validation
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f2f49e9a-5f1e-4a57-ab83-295ed03ddabb)

cert now issue and to view it 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/dd73305b-63c3-46e4-975f-81c227a4ad7d)

go to beanstalk and let create a https server for testing
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8d9c556d-b931-4973-8e12-89a2cc876b9b)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/21cc52a9-0641-425d-ba9b-67ad4994dc7e)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1a10b190-bf3e-470f-b5bb-92fec7cdf71b)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/cf1464e3-4dcd-441a-8f56-cd53ad37925e)

configure more option
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fc883452-8fec-4c41-bb3c-4760f03500bd)

modify load balancer
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b6ef78d0-e98e-400b-94a7-e8e64aa4c56e)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/34fbe897-09f1-4c9f-a577-7efd29c015f6)

add https listener with our cert and ssl policy 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/76d9bc3e-f398-4dbe-aa2a-d52ad750c19c)

Load balancer setting 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/eae43c08-bf82-45fa-af2b-08a45e6237dd)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/47802920-4216-4328-8d3e-552702fe8cb5)

Save and create environment 
simple beanstalk app
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d652c030-7cb9-456a-960b-f9242daac9be)

Created beanstalk app
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/71a2c38d-2e8b-4d53-a0b5-8ec64a53514d)

URL not what we want and not secure
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b096bfda-b846-4332-9bca-322465ff6aaf)

we have to create a cname record 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a75b5290-acd2-4689-93ba-c1f3356312dc)

go to hosted zone
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e0ff868f-840c-489e-9391-c4df5622a15e)

your domain
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2a9d46b1-81a6-40a6-92f4-7c2306e1d087)

create c name record set
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/26594131-7823-40af-b6b3-a9522ee024d7)

access to our beanstalk using this cname and still not secure
we did not force https
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e9275cc0-341b-4320-8874-cc8ed514dd1a)

go to https://beanstalkapp
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3b0ec3cf-a879-4331-9b78-cefc22a17702)

connection secure and valid
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c7e42d4a-afbb-4575-b182-30cec0bf258e)

go back to acm and you can see it in use
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/920e8136-7e76-4903-b35b-d9d5e9ca2a52)

our load balancer and tls config
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3210a62c-d324-4c82-a647-ac7284b453c6)

