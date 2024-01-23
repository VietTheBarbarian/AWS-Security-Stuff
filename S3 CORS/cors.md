Practice using cors
first we must changed our index html to enable cors
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/5211944a-8fb6-4443-9c78-f47185fc1c35)

The index.html will fetch and extra page extra-page.html
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/fddcd32a-910d-41a3-af50-b2be4f2b02ac)

Let go into our bucket and upload two file 
extra-page.html
and index.html
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1ab88da3-787a-461c-8a9b-b79c856cf36c)

if you got into bucket properties and look for endpoint of the bucket 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4479f79c-8963-4e31-8f10-45b1de15e60b)

Click on this 
and see that the fetch request work on the same origin since our s3 bucket has the html file in the same location 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/cf830605-cfff-4ba4-812f-22e2eb5e7ffc)


![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/7e3fa8ca-5e5e-494f-8dbd-d3c1467e9f9c)

Demo of CORS starts here:
Create another s3 bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f4fa2081-747a-4751-84c4-631b64edae61)

lets make this public
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9fee2cb8-bc57-4441-88b3-1c99a3b42a23)

Go into the bucket and properties
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4f27d282-bd1c-4081-9264-e267860f3e08)

enabled as website
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/743ec14f-b039-44b2-adc0-6e661be6f0df)

index document as index.html even though we dont have one
save changes
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/969bcd48-8465-4f71-949f-2544643e7b66)

edit our bucket policy
use the same policy as before
remember to swap out the bucket arn
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/060a8fb3-b276-47f7-b886-c30b5bcca8f8)

save changes
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/02ecf5a8-c099-49c4-8c3b-723349509820)

back into our bucket upload extra-page.html
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/67538a5b-72a8-4400-8f18-bb2374ef0d64)

should be public
click on object url 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/62656436-8ff0-41ed-b4c2-59cd2b80bf67)

extra page is loaded and file is public
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/4d5d62ed-0fa2-474c-a4f2-af7a8467f528)

Remove the extra page.html from previous made box
this will be our origin page
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6161216c-c752-4d3f-be0e-9b277eefed0c)

We also need to changed the index.html in the previous bucket to point to our extra-page.html on our new s3 bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8eb7fb0f-4872-4d37-8e64-6419ecf462ea)

Copy the public url of the extra-page.html on our to our index.html from our previous s3 bucket 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9e4db311-b987-406e-bbae-21fb0f6af8a5)

use this entire url and changed our index html 
we wll fetch the extra-page 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/efdf942d-2294-40e1-8d59-0497e0424b28)

upload this new index.html to the previous s3 bucket.
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2f7e0d28-95b2-4586-9aed-cf855c89ca20)

open the web dev tool and we will see that we have a request blocked
we have Access-control-allow-origin missing
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a9662ec3-1295-476d-96b1-f2e233a087a0)

the new bucket is not setup for cors yet
and the request if failing 
Lets add the cors setting on our new bucket and we have the CORS setting and edit
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/f92db455-60af-45c8-a14c-f4b8a4738177)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/6640cc6c-b4d1-4a56-b016-dd7be9d0c122)

allowedorigins to the first webpage
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/de106e0a-e1a6-45a7-9be9-114eab1985fa)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/20f51b0e-b55c-44f5-a391-93546c453962)

Correct:
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/35738837-b189-4487-812d-e360ab56faef)

if we look at the networking tab we get the extra-page.html
response header
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/2e198870-3601-40d7-99fa-93ccf1686c34)
