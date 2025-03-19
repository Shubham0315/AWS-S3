# Bucket Permissions

1. Create IAM user without attaching any policies

![image](https://github.com/user-attachments/assets/020691d0-5461-451f-81da-353a1d58a49c)

2. Login using the IAM user. 
- This user cannot access anything in AWS console as he doesnt have any permissions/policies attached

![image](https://github.com/user-attachments/assets/0721b112-094a-4203-b3ce-05516a7d23e7)

3. Attach policies to user
- Add permissions - Attach policies directly - S3/EC2 full access
- Now user can list the S3 buckets
- Even the file in S3 is very sensitive, as IAM user have full S3 permissions, he can download that

![image](https://github.com/user-attachments/assets/61696702-3f1f-4654-90b5-235542a0ac13)
![image](https://github.com/user-attachments/assets/938dfced-0cdd-495c-b887-0fa2c56f5cbb)

4. Restrict actions using policies
- Now as devops engineer we dont want anyone to access buckets even IAM user has policies to do so in attach policies. We need to restrict access of IAM users to access S3 buckets
- S3 - Bucket - Permissions - Bucket Policy - Edit - Add JSON statement
- In Sid provide the statement, principal means who we want to perform action against, effect means allow/deny, in action just type s3 in search box and select s3* to deny all access, in resource just add resource and provide bucket number

![image](https://github.com/user-attachments/assets/f92f8a1e-4a09-4086-a911-a36f16173a5d)
<img width="959" alt="image" src="https://github.com/user-attachments/assets/e722da0d-51e9-4e89-9b70-8791720269b9" />
<img width="959" alt="image" src="https://github.com/user-attachments/assets/fac537bf-9bb0-4ea5-a3f6-07fb5fa6e9ef" />
![image](https://github.com/user-attachments/assets/f777e6fb-51d5-4dde-86aa-2aa5d2ebc5a0)

- Here blocking everyone means blocking yourself as well. Bucket owner to have access so add condition
  - Select principalArn - Add operator as "StringNotEquals" as owner to have access - Add value of Arn (use account ID there) - Add condition
  - The file looks like below where we're denying access to our s3 bucket, all objects inside it except owner.
 
![image](https://github.com/user-attachments/assets/e9f1c2c2-2d05-43c7-afdf-ad8fdadc8f64)
![image](https://github.com/user-attachments/assets/f11f35cb-84cb-4a18-b2bc-746844da5c64)

5. Login by IAM user and try to access buckets
- IAM user have permissions to all S3 but cannot list objects inside bucket. So he has insufficient permissions as we've updated policies for other users than owner

![image](https://github.com/user-attachments/assets/b5638a8b-270e-4e54-86d0-f57ff4a02707)

