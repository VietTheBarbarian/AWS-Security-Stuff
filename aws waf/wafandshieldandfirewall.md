WAF and Shield and Firewall Manager hands on 
Layer 7 protection for exploit 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/220bd8e5-05b3-4097-a19a-2a62ea1c7caf)

We need to create a web acls for this 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2176428d-912f-4ae7-8e9c-ae0dea5b9a12)

whether or not its for regional resources or cloudfront distroubtion which its going to be global
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/10b79f0b-61f6-43f5-9edd-86d9ca5471ae)

we can associate aws resources with it 
which resource you want to protect with your web acl
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b6863097-c7d4-4161-a198-886f0a6499a0)

Next

We can add rules to our ACL 
We can create our own rule or add managed rule which are rule chosen by AWS and partners
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/75c2a9ef-6ad1-40e0-a42e-1e4da3c724aa)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7ac65b34-0200-4597-9d3c-d4175ef57998)

We have many managed rule such as bot control and account takeover prevention 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ab5b8efe-95cc-42e5-a120-c9a32b5fb9b8)

Let choose anonymous ip list 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/311c3871-c5aa-4467-91db-c5a9ada84944)

here the overall rule we added 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a050a279-99b8-4cb6-a216-933675d4edb2)

if it doesnt match any rule than the default action will be to allow it 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3bce9115-1722-4989-bcf7-e43010dd6ba8)

set rule priority if you want

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/627d789e-d09a-4bf4-8f80-dbf9c4eedafa)

set metrics if you want
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0bce1a3e-52fc-4243-970a-5367eacfbc07)

Summary of rule in the end create
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4e8602e2-116c-412e-8de0-a662e56610e4)

We can set up ip sets
what to block or what to allow
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/be55a3b0-9f63-4d33-94b5-144d24a21c01)

Next we have shield which is ddos protection its expensive 3000 dollar a month 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/223cfa7b-fc06-46e6-b171-20a245a3cc95)

Firewall manager is also expensive
Will allow you to create policy across accounts
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1135f68a-f5ac-47ec-822c-7d89d0fd6f26)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/65ca0240-5fcf-4b79-bb3a-311f0d159f50)

