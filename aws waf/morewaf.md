Prevent exploit to api use webacls

IP set
a set of ip consider to be in this ip set
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/285f8561-2304-4aef-b83d-8f629669dbe1)

Whatever you want enter your cidr
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d653ef26-374f-4387-a1c5-8b3be766094a)

Go to web acl
choose which region your in and create a web acl
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5a86cb3c-d1fd-4b8d-85bb-27edf7548ac1)

Give it a name 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/85ab0778-eb12-47ee-b1df-5573ba66ca78)

This is associated with cloudwatch metrics
And which resource you want to protect
will choose our regional resources
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e541b1ed-9788-4deb-a753-ca5352bed511)

optoinal but you can associate aws resources like load balancer 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6cd175b5-edb5-4440-a880-3fa7c31a3df3)

need to add rules and rule groups

ACL rule cannot exceed 1500
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e02fe44a-e3e5-4c84-9596-2922c96ff8ed)

Add some custom rules this time
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fe804e55-2f46-43b9-bdde-2262a134a06e)

Choose our ipset
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c8772f4e-6421-4457-abe6-cbeaa697fab3)

for this ipset you can choose action we will choose captcha 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5c53cfc5-a3da-4e16-82dd-221cd76359bd)

If we want to block everything that not in the ipset there wont be an option for that 
so you have to go through a rule builder 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b1bd0d27-7929-4fbe-b592-aa9adf57368f)

If you use a rulebuilder you can block anything but ipset using conditional statements 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bc9bac19-56c6-4063-a4f8-44baf451593c)

if your  request dont match the ip set than blocked 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7e0fa460-e36f-40d2-8b00-6735e810106f)

IP address to use as the originating address its best pratice to use source address 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9cdda252-c0eb-4c7e-bc9f-fd27429accb7)

dont want use use the IP address in header cause header can be modified 
add this rule 
WE are good
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2477473d-74e6-4ee9-997d-b52540d6db6b)

add another rule to rate limit
a rate based rule 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3c0c336d-824b-4d7c-a4cd-cebb3beab657)


Our rate limit will be 100 request if it reach this than it will be blocked for 5 minute 
look at source ip address to see where this is coming from 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a91fbb07-48b4-4c51-a8c4-d8ced66a5063)

we can also count request that match a specific request with conditional statement 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e5c378a8-f7f9-4e33-9334-253b8d551cff)

We will do all request and block in this 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/55071fd6-a8f2-4dcf-959b-cdb3953335ae)

add our own rule for sql request 
lets block sqlrequest from body 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5d403019-6f3d-4bd8-b05c-bc98033c8279)

if the body look like a sqli than block
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9bb58f8c-8c0e-4887-b7a3-391f6fbdcc2f)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/53f0f5ba-9b19-43a9-83e7-0f38b2dc0fec)

important low is a better choice forsensitivity level for this rule 
high level valid may be seem as sqli
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5c0571d1-bf10-4877-9fcb-c8124bd84895)

if  size of request is too big than its best to continue
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8747cde7-482a-4907-b85c-03276671224d)

create webacle 
we have created our first set of acl/protection for our ipset on our waf
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/56c87ed3-1f24-4dde-b358-3f7382b0b33f)

another thing to look at is rule group 
So, rule groups allow you to actually create these rules as a group, so it's a little bit faster to create Web ACLs
by using rule groups, 
