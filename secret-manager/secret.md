Creating a new secret
Note: need username and password for databases
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0b2a41fb-536a-4707-bbbe-39dd6f2f9cbc)

If you go on other type of scret we can store a key value pairs
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ad4ba028-a724-4f5e-a508-6c9f20060d11)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c51d814e-c45a-4714-a0e8-8db47592e5e9)

You can enter in the UI or a json document
This will kept secret. To access you need apropriate IAM 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4985d666-9010-42e3-b420-b589b4f3e87e)

options to encrypt
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0f276b5a-1c14-44e8-9ab0-bb2bb37dcaaa)

Name secret and description
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/cc2cf17e-805c-418d-a25b-8938702ab72b)

Resource permission for for access secret across AWS account 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0faf7a5c-8f12-4ac1-902e-c54290318d1a)

Replicate secret 
good for multi region setup/disaster recovery/HA
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a1318b21-91b7-4e16-893d-acb316338e74)

We want to automatic retotate our secret
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/47b843bc-6bd4-4348-8a91-befb8169f1ae)

We need to specify our rotation function/lambda to do rotation
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a79b5e26-2585-49f4-950f-e542817a1ab6)

Some code if we want to invoke and get the secret from our client 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6fc74f42-476e-4bec-b26e-cd429e7ac3cd)
