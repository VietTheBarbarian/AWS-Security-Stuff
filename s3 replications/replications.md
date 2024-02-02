Create a new buckets
targer bucket | replicated bucket
Replication will only work when versioning is enable
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b1d1eb38-edfe-4648-ad4e-a246e7753ef8)

In the target bucket upload your files
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c890222e-e1cf-4f18-ab0e-166282cd1102)

replicated bucket 
management and create replication rule
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a745527e-36bc-4570-9bd7-5a25f2c6f996)

specify the bucket you want replicated 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a68fc483-add1-4c6b-8c41-c73ef344ed25)

might want to create a new role for this
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/de3f3c0c-ca52-4ff0-907e-6bf91b4e556e)

when you enable replication it will only replicate object from the moment you set it 
You can use something call batch replication to replicate previous obects but we not going to do that here
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0af1a545-b072-4388-9a0b-66ee2f35d7a7)

have to upload new file for it to replicate
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6fbc6b2a-8a7c-4654-91e7-b2ce57641c26)

Will only replicate that new file 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3c6ca64c-1980-41e4-a0a0-373df6a5f0a5)

if you want the previous file to be replicated you need to replace those file
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b95dd51d-50c0-4cad-bc7d-05a7a80bf1a2)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d77ddf2a-5252-4cf5-9348-d0a898a568cc)

Let look at another setting
delete marker replication
So by default, delete markers
are not replicated
but there's a feature to do so.
So if you enable delete marker replication, then they will be replicated from one bucket to another.
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e7196535-1320-43b1-a483-3a5985476d77)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a3c450a0-2a49-4296-8b85-4fef4184801b)

delete marker replicated
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/aee15975-00bf-47a3-aeae-25d2591ac02b)

