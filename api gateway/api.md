we are in api gateway
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1cc65d39-b8c1-4738-92ef-c4682bb97b3e)

Choose an API type 
we will choose restapi for now 
Build
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bd321831-dff0-4888-b9b8-a1713c875c2b)

When you build an api you have serveral option you can create import clone or example api
for us choose new api
Choose regional to keep thjing simple create 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/24318a65-f24a-4945-81e8-839db8c9e033)

So let create our first method and choose our emthod type 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f05fc6c0-cea2-41df-98e4-dd5461e946ff)

Choose our method type 
Do a get 
And choose our integraiton type we will do lambda function
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2b9388c3-d17b-4e30-a0fb-18e59fb5ce3d)

To use this we need to create a lambda function
Create a lambda function to react to this api gateway
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/596decfd-5107-43b3-b9fb-dd9392b678df)

This is our function
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4df214ed-06ed-4a09-ae31-01d314f4aa81)

The code we going to copy to lambda
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5faaff2e-8362-405e-a8df-66755af9af63)

Paste our code and deploy
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1f120c05-fd4f-43a5-9054-71467451b653)


![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bda2eddb-d136-41d7-964d-aae96acefccc)

We can also test it 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b8894b65-ad28-4fcc-b23b-6f2ca3f83551)

Send this event
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/67aeb2b0-7561-48a2-94e7-13c33e696341)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3f537a52-6b11-4a1c-8030-d4cc46bb1b33)

Than test
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/55151971-7799-440b-aee6-77596b48c840)

Working fine
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1590c0f0-0d88-435b-a24e-09c4d395e9f3)

Now to integrate this lambda function to your api gateway 
Copy function arn
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c921c2f9-f5b5-4fb8-a3d7-80e9f6f18202)

Go to api gateway and paste 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a883c5aa-c505-4dc5-88f6-c055ee977bf4)

See full request pass to lambda and back to lambda check 
Lambda proxy integration 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fcc0f3c1-7432-47eb-8c77-9022d98050e1)

API Gateway has a limited timeout
and the default is 29 seconds.
You can customize it and have it less than 29 seconds
but the default timeout is 29 seconds regardless
of how long your Lambda function takes to execute.
So let's create this method
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ad9d376c-f0f3-4105-8887-345e1394de05)

and this is going to automatically grant API gateway,
the right to invoke our Lambda function.
We can see that our api gateway can invoke our lambda function
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/bcd430f1-83d4-46c0-9103-e8343ebb58c3)

Verify  this by going to configuration and permission 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f4ff9d1d-d2e8-483a-85fd-79fae410b7ed)

Look at our resource -based policys statement.
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1b471f27-f7d6-4716-afd7-8947b5006bd8)

View policy
apigateway is allow to invoke lambda function if the source api is the following
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/936b0879-2091-4d61-b71d-52184c5011e8)

Flow of what happening
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3de0de18-854c-40b4-b69a-e0b9f3262a45)

test our api 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d3a77235-f073-4304-933d-7775f4d4a589)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/91b046ac-af6a-47c8-b1d4-0cb6c7bc3528)

Click on test
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6c0663c9-dc26-41d9-89cf-e63a576691c1)

let debug this and see whats happening to our lambda function
print(event) than deploy this
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fb4e7177-fd7f-4eb1-a0fb-10369f0dd933)

invoke our lambda functiona by running test
Still samething but this time we ar printing  event 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c288e919-f0d0-44c0-ad31-1fa5d6d32c5c)

if we go into moniter than we can see our cloudwatch event
monitoring 
cloudwatch logs
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4015ee36-8bb0-4485-94df-861b2ce40541)

Our latest log stream
this is our print event 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f52dabf7-42fd-454b-883c-6dd7d5d5fedc)

So now let go ahead and create a new resource
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/3499ea8f-db0b-4db3-9ac4-f1826fd7f499)

Our resource path is this and name is the following
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a10762b0-d2ea-415b-8468-f7f3a3854c52)

Create 
Now we have a /houses path
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/ed9ea2c9-81b6-416c-9fe6-1fa3cbfc9d6b)

in /houses create a method
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/479549e2-6278-438f-8811-4751bed0a861)

Get again and create a lambda function
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/18a72362-17d0-4724-a1ac-ce6c64496af3)

Need to create another lambda function
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6f53fbc6-d4a1-4950-b3ba-f77b327ea638)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9e775370-7b16-422f-8cd5-321c7022cb49)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1fe68088-3cdb-48d8-a6c4-6ac97b4a5a55)

Copy function ARN
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6e06ba08-09d9-4baf-9d8a-f36aa594fe49)

Paste arn and create method
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/02c8af0a-d688-4eb7-bfea-3e79b172ddf5)

Now we have /houses with the get method
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7c673e24-41cf-4d84-aae9-b6768ead32e6)

Test 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5386a700-1271-41cc-919c-3e00f3332b29)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/47122d9d-aefa-4392-ba19-83f16629af87)


We have root get and the houses get which invoke two different lambda function
Deploy api
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8e04f7ac-5ca0-41f9-8a6a-b0019dafff80)

Now that we deploy this api we have the invoke url
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6859eb6a-77d7-44e5-80ed-c067cd23ad91)

Copy and paste url
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/c0f4cb51-be31-464b-a52b-f120e8264312)

go to /houses we have the following
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a2b70841-d96a-4e98-9b53-56b03f0d178a)

Do a wrong directory we get error message
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/cbf05f23-0c06-4ea7-9ca1-3f46dcd62a24)

