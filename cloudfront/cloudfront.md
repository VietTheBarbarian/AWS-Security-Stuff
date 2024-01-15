Create a s3 bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/09a21331-1b49-49ac-8c9d-b1229668682e)

Upload some file in it
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/821fb5f7-6196-4bff-b88c-5154361465fc)

access object via object url
cant access it cause object is not public
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fdd535e7-3cf2-4730-b484-18e111c3761a)

open button to open a presigned url 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7a2bcec9-09be-46bb-8f77-4ee03067d984)

Allow you access it but the image cant be seen because it not public
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fef61f19-ad26-489f-a127-76d322a7d95d)

So, let's see how we can instead use CloudFront
to make these files accessible without making them public.

Open up cloudfront
note cloudfront is a global service
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/0d672d26-b3c0-40a6-a6ca-238029125e1b)

choose your bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/de39f144-72df-4e3c-94a5-b2edd630ff8c)

Origin access
how you access the identity 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5c598d72-37a1-4a28-a53b-c31512b9dfb8)

Choose OAC.
Legacy is OAI which old way we want new way
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/92a8229c-dae7-41fe-b89f-9097137f4688)

Create a OAC 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/542a51a3-1c84-4a89-8bb2-1b16cbcd5019)

Create
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/22827eab-354b-4d2b-8692-827bf2f34f42)

Now it created now we have to update our s3 bucket policy 
so that cloudfront can access our s3 bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ebdc8a09-354e-47df-8d24-052747fb4c79)

Disable WAF cause this is a demo. Please check with the owner if your doing prod stuff
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/67f0d360-86c2-4017-a725-01c81262dbcc)

Choose our default root object
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/65eac124-793f-4f0e-b3c9-7f3986e91ea7)

distrobution is created
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6aa1133d-7a57-428a-813b-ef39622c254b)

We also get a shortcut to update our s3 bucket permission click on it and also copy the policy for cloudfront to access it
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/449a6b2a-100f-4d23-a7d8-b593631b94ab)

Paste policy
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/edb8352e-7a70-4fa0-b6e0-041f1447e9ba)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/071be3cb-6089-4fb6-9ed5-2b344c4e9fcd)

If you lose your policy go to distrobution orgiin 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3fc22872-b2fa-4514-9ff8-61fc800635e8)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6554ba46-97d2-46ee-8b5f-d92af5334df6)


Wait for deply
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/53ae236e-c5f3-4e2c-bef8-eec097a9eaec)

Copy domain name and now you can see your image
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b109ba78-84e5-4801-8b8f-e908205c02a0)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/40a8f19c-7937-494f-8646-47bd20b61684)

This is serve from the platform cache not the s3 bucket itself so loading is quicker too 
Our origin access control is found here too
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5add0617-a032-42c5-bf6f-f883e03f6d58)


