Every sql command is found on the documentation page 
https://repost.aws/knowledge-center/analyze-logs-athena

Using athena service to query data from s3 bucket
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/d117143f-cafb-47c2-b6c7-92ce45af1b50)

Before you run your first query, you need to setup a query result location in amazon s3
View setting 
Manage setting
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/b4fb8e5b-967f-480c-b29a-5ecd38f1b6e2)

Create a s3 bucker
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1781eb79-0c2c-46da-9e7f-d13d21c3ffd0)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/8e8aeef1-c61d-411b-bab0-89609fad6c53)

Copy bucket name
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a47209dd-cf20-41a2-b6e3-40df9b67c06e)

save 
this will be our query result location
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/9b0a213a-18db-4f20-91b0-85648bc3e5a0)

Go to editor and you can see that you have data sources
And Databases
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e912e085-3d2a-41e5-9797-6f14b83d0304)

Create your own database
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/1bf18e57-efc5-4a93-a743-4eb98446e5bd)
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/215c45f8-df09-45d1-aa5c-f3699a71c9cd)

Create external table
```
CREATE EXTERNAL TABLE `s3_access_logs_db.mybucket_logs`(
`bucketowner` STRING,
  `bucket_name` STRING,
  `requestdatetime` STRING,
  `remoteip` STRING,
  `requester` STRING,
  `requestid` STRING,
  `operation` STRING,
  `key` STRING,
  `request_uri` STRING,
  `httpstatus` STRING,
  `errorcode` STRING,
  `bytessent` BIGINT,
  `objectsize` BIGINT,
  `totaltime` STRING,
  `turnaroundtime` STRING,
  `referrer` STRING,
  `useragent` STRING,
  `versionid` STRING,
  `hostid` STRING,
  `sigv` STRING,
  `ciphersuite` STRING,
  `authtype` STRING,
  `endpoint` STRING,
  `tlsversion` STRING)
ROW FORMAT SERDE
  'org.apache.hadoop.hive.serde2.RegexSerDe'
WITH SERDEPROPERTIES (
  'input.regex'='([^ ]*) ([^ ]*) \\[(.*?)\\] ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) (\"[^\"]*\"|-) (-|[0-9]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) (\"[^\"]*\"|-) ([^ ]*)(?: ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*))?.*$')
STORED AS INPUTFORMAT
  'org.apache.hadoop.mapred.TextInputFormat'
OUTPUTFORMAT
  'org.apache.hadoop.hive.ql.io.HiveIgnoreKeyTextOutputFormat'
LOCATION
  's3://awsexamplebucket1-logs/prefix/'

From <https://repost.aws/knowledge-center/analyze-logs-athena>
``` 
Properties will give you the name
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/021c36f5-c935-4087-b321-2447f57188b5)

Run
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/e2cdbdc5-42b0-4160-9202-5872f1b298f4)

On the left we can see your tables and columns
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/009de1e1-51f3-44ac-a143-9212794660c3)

test with preview table
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/a7dda363-80d6-4ef8-89fd-8ea72b233fe2)

Will generate a select all with a limit of 10 
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/27554ace-625b-415c-be58-6e137e61362a)

More sample query
Give us report of status code and how many time it occur
![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/40b580bd-ff34-4523-9b2c-f5b002f9e8cc)

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/049176f3-c084-4b9d-ba3d-fbcfa9610e48)

Checking 403 for unathorized access

![image](https://github.com/VietTheBarbarian/AWS-Security-Stuff/assets/56415307/126af898-ff79-47de-b46b-790a3cfafa72)
