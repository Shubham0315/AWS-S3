# AWS-S3 (Simple Storage Service)
This project describes how AWS storage service S3 solves the problem of storing data on cloud

- S3 is one of the most easy service of AWS. It solves the very common problem of storage
- For our personal stuff/data on like mobile, laptops we run out of storage and copy our data to hard disk, pen drive. 

- But what will organizations do as they have heavy database? In organizations we deal with heavy databases, database dumps, continuous backups, application logs, dashboards, charts, csv's.
  - As most of the organizations are moving towards public cloud. The solution in public cloud is AWS S3. It is a storage service solving the storage problem
  - Simple Storage Service :- S3
 
- S23Characteristics :-
  - Highly scalable
  - Highly available
  - Secure
  - Cost effective
  - Performance
 
- S3  allows you to store and retrieve any amount of data from anywhere in the world
- If files on our laptop are there in S3 on cloud and they get deleted from laptop, we can still've them on cloud.

------------------------------------------------------------------------------------------

What can we store on S3?
-
- S3 does not have any restrictions we can store anything.
- Normal person can store Pictures, videos, files, folders, excel, reports
- As devops engineer we can store App log files, database files, dashboards, app config files, excel sheets in S3 buckets.

- Sometimes when we take backup of data dump, it can take 3-4TB of storage. Thats where we can use S3.

- Anything we upload in S3 are called OBJECTS and they're globally accessible.

- Anything we upload on S3 bucket is accessed by HTTP protocol so that the S3 becomes globally accessible. So we can put our DB files, app logs can be accessed from anywhere in the world.
  - e.g:- If organization in US upload info to S3, people in India can easily access the same using http protocol

