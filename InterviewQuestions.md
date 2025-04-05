What are S3 storage classes?
-
- AWS Offers different storage classes designed for various use cases based on access frequency, cost and durability.

- S3 Standard
  - Used for frequently accessed data
  - 99.99% durability and availability
  - Highest cost
  - Used for websites, apps, logs, hot data
 
- S3 Intelligent Tiering
  - Used for unknown or changing access patterns
  - 99.99% durability and availability
  - Cost lower than standard
  - Used in data lakes, analytics workloads
 
- S3 Standard IA (Infrequent Access)
  - Used for infrequently accessed data but needs quick retrieval
  - 99.99% durability and availability
  - Cost 40% lower than standard
  - Used for backups, DR, long term logs
 
- S3 One Zone IA
  - Infrequently accessed data that does not need multi AZ redundancy
  - 99.99% durability and 99.5% availability
  - Cost 20% lower than standard IA
 
- S3 Glacier
  - Used for long term archival storage
  - 99.99% durability and availability
  - Cost very low
  - Used for cold storage
 
- S3 Glacier Deep Archive
  - Used for data that is rarely accessed
  - 99.99% durability and availability
  - Lowest cost among S3 classes
  - Used for regulatory backups, scientific data
 
--------------------------------------------------------------------------------------

How is data organized in S3?
-
- In S3, data is organized in flat, object based storage structure, not hierarchical file system like traditional file systems.

- Buckets
  - Top level containers for storing data
  - Each object in S3 is stored inside bucket
  - Bucket names must be globally accessible
 
- Objects
  - These are actual data/files stored in S3
  - Each object consist of key, value, metadata. version ID

- Keys
  - Every object in S3 is identified by unique key
 

--------------------------------------------------------------------------------------

How do you upload and retrieve files from S3 using AWS CLI or SDK?
-
- We can upload and retrieve files from Amazon S3 using either AWS CLI or SDKs

- Using AWS CLI
  - Upload file :- **aws s3 cp $file.txt s3://$bucket-name**
  - Upload file to Folder :- **aws s3 cp $file.txt s3://$bucket-name/folder-name**
  - Download/retrieve file :- **aws s3 cp s3://$bucket-name/$file.txt ./local-folder/**
  - To list files in bucket :- **aws s3 ls s3://$bucket-name**
 
- Using Python SDK (Boto3)
  - Install boto3 :- **pip install boto3**
  - Upload file :- import boto3; s3 = boto3.client('s3'); s3.upload_file('file.txt', 'bucket-name'. 'file.txt')
  - Download file :- s3.download_file('bucket_name', 'file.txt', 'downloaded_file.txt')

--------------------------------------------------------------------------------------

How do you make an S3 bucket public/private?
-
- In S3, bucket access is private by default, but we can change acc to requirements
- To make private
  - Go to bucket - Permissions - Block public access (all select)

- To make public
  - Making public means anyone on internet can access it.
  - Go to bucket - Uncheck block public access
  - Set bucket policy (for specific access)
 
--------------------------------------------------------------------------------------

What are bucket policies and IAM policies in S3?
-
- Using bucket policies and IAM policies are key to manage S3 securely and effectively

- Bucket policies are attached to bucket while IAM policies are attached to user, group or role
- Bucket policies controls access of specific bucket and its objects whereas IAM policies control access of all AWS services
- Bucket policies are used for public access, cross account access while IAM policies are used for internal access for users/apps

- When both IAM and bucket policies exist or used together, both must allow action for access as deny takes precedence over allow

--------------------------------------------------------------------------------------

What is the difference between ACL and Bucket Policy?
-
- ACL
  - Controls bucket or object
  - Has basic permissions
  - No JSON
  - Limited cross account access
 
- Bucket Policy
  - Controls bucket only
  - More granular in permissions
  - JSON
  - Cross account access support
 
--------------------------------------------------------------------------------------

What is S3 default encryption?
-
- It ensures every object stored in bucket is encrypted at rest, even if upload request doesnt include encryption settings
- When default encryption is enabled, every object is encrypted auto, we can also choose own encryption when uploading

- SSE S3 (Server Side Encryption with S3 managed keys)
  - No key management needed
- SSE KMS (SSE with Key management Service)
  - Uses own KMS key
  - Gives control over key rotation, logging
 
- To enable - Bucket - Properties - Default encryption - Choose any one KMS or S3

- Default encryption only applies to new objects

--------------------------------------------------------------------------------------

How do you restrict access to a specific IP or VPC using S3 policy?
-
- We can restrict S3 access by IP address by only allowing access from specific IP or IP range using condition block with IpAddress
- We can also block other IPs to deny traffic. It will take priority over allow

- To restrict S3 access by VPC endpoint
  - This restricts access to S3 only via specific VPC endpoint, it is great for securing access within AWS network
  - To find VPC endpoint ID - VPC - Endpoints - Copy ID
 
--------------------------------------------------------------------------------------

What is S3 Lifecycle Management?
-
- 
