PrivateLink hands on 

Create endpoint service
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/cb4c03e5-415a-4170-bc2e-a5413ca9264c)

Chooose load balancer type 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6c9b5c2a-2a0e-4067-b1c0-cf1b2fd7fb35)

Specify a network loadbalancer that you might or might not created from before
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2f8ad8a9-6be1-48b8-9033-7235126e976c)

Once the nlb is set up you can specify additional settings 
What ip address type you like and if acceptance is require or not 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3a6c8009-44a5-4cc8-9325-8c196ea24f06)

Endpoint services should be created here 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2c48e33d-3f6c-44f3-a75f-eece2e216862)

To link to VPC go to endpoints 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2793c2e0-83c2-4f08-b3f8-bef2a6daad01)

Create endpoint 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/765ef6dd-4c31-4826-9df9-94b2712a7ab2)

Use other endpoint services
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6b24d5f5-56c6-4f3c-bd90-6b10d0eb43a6)

Type service name you made from previous step
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8cb5df69-1fee-48ad-9582-3f5d936ae223)

Than select your VPC 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/beaaf1f2-ae3f-42c8-a338-6535067df54c)

You now have private connection in one service vpc to another vpc without having to go public
