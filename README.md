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

------------------------------------------------------------------------------------------

Creation of S3 Bucket
-
- Go to S3 - Create Bucket - Provide name (unique as it is globally accessible) - Choose region - By default public access is blocked - Enable default encryption - Create bucket
- Though S3 is global, we need to create it in region. We create in region but it is globally accessible. Most of the AWS resources are created in region due to latency problem.

![image](https://github.com/user-attachments/assets/5a42bf36-f0dd-4142-838c-7a494a228a47)
![image](https://github.com/user-attachments/assets/c48f37cd-c036-4c81-99f7-a91f7d204858)
![image](https://github.com/user-attachments/assets/bfd8bbc5-4434-4fc9-b944-7db25a4e49f7)
![image](https://github.com/user-attachments/assets/b1b36c26-4594-45e0-a73d-d86f844c8847)
![image](https://github.com/user-attachments/assets/eb134b6f-68d7-4b63-97b3-9c2d3966b882)

- To upload information in the bucket
  - Go inside bucket - Upload - Add files/Folders - Upload
 
![image](https://github.com/user-attachments/assets/5eb8f22e-0110-4174-a936-e49b7199aa68)
![image](https://github.com/user-attachments/assets/8e5960d2-7d39-4996-929c-62302abd33f5)
  
  - Now the files are uploaded to S3. Even if it gets deleted, we dont need to worry as the files are there in S3.
  - e.g:- If organization in US upload info to S3, people in India can easily access the same using http protocol

------------------------------------------------------------------------------------------

What if the region goes down where we have created bucket? Will the data uploaded is accessible?
-
- AWS guarantees even if we upload 1 billion objects in S3, only 1 will have error in accessing (99.99999999999% reliable) 11 9s after 99.
- So we can assume our object in S3 will never get deleted.
- This is due to replication mechanism of AWS. Whenever we store the object in S3 in any region, AWS creates multiple replicas of the object. In a region there are multiple availability zones, in zones there are multiple data centres. 
- AWS create multiple replicas of single object so even if any of the zone, data centre goes down we will have copy of the object so that it is replaced automatically in availability zones which are identical.

------------------------------------------------------------------------------------------

