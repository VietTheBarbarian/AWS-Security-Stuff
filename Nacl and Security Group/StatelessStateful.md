Looking at nacl and security group
Default nacl
alloweverything  inbound allow everything outbound

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/adebdbf0-9a54-4de3-8f42-8bd7263c7bf4)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/87cad317-d4d4-436f-8ba5-e6f1b6c31ad0)

Default nacl are going to associate with any subnet you define 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c62644c1-8f7c-4b81-a6cc-6934b8bea6e6)

Go to ec2 instance and connect to your bastion host
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f7ace89f-2786-47b9-82f0-cacb8c5d53ea)

start web server 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b7060bfe-fc30-4a6a-8a7d-d910b25d2c2c)

Echo hello world into our html directory 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5eadb4b6-8f83-4c30-9250-1606411dc9b5)

Make sure this public instance has http enable on our security group. Right now we only have port 22 ssh
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/43a68779-4e94-4c5a-b6fa-7d8ef0858f1e)

Go to security group
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8a40619c-f17d-4295-baa3-1e0ab7c6d585)

edit inbound rule
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8155de95-79fa-4880-9d4e-64282912d0be)

add a rule
allow http from anywhere (0.0.0.0/0)
save rules
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a3671f18-ba1f-49f5-b2e5-740e14d29b67)

now copy our bastion host public ip and paste it into your browser 
you should get hello world 
we are able to connect inbound
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c03af641-67b9-4780-8bb7-05f5117d7fe1)

now let look at our nacl and edit rule
let add http deny rule this time
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2a922269-eeac-4ab8-b75e-a82021e0a39d)

now if we go back into our public http we will get a infinite load 
nacl acting as a firewall
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3551fc01-3891-453e-a74d-be5064495c85)

if we change rule number to 140 for our acl that block port 80 
the page will load
since rule 100 take precdent over rule 140 kinda like top down rule
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2c914a91-5e78-45f0-99e9-9078a5218008)

now let edit our outbound to now allow port 80 outbound on our nacl
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/23246f0e-4070-47ab-80f8-f1bcfa4b74d4)

inbound rule allow outbound rule deny
so infinite loading 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/46f0ed23-6199-4816-9450-1a3e2b597fcd)

overall lesson acl is true regardless if security group of ec2 allow for port 80 in
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d694a4f3-1874-45a5-8a4a-9435f9529ca2)

nacl and security group work hand in hand together
revert everything back 
another demo
remove outbound rule from security group 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1a021b58-9da8-4ba1-a276-8040235c3150)
since no outbound if we refresh it will still work
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d03328e0-4f30-473d-abd3-995278514106)

the security group is stateful.

That means that if the traffic is initiated from the outside

and is allowed inbound,

a connection to Google account, for example,

it would be denied because,

well, there's no outbound rule that specifically allows it.

then the return traffic will be authorized as well.
