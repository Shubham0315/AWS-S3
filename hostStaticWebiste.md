# Static Website Hosting

- S3 is very cheap solution to host a website although we can use route53, CDN, cloudfront.

1. Create bucket and upload object

2. Bucket properties
- Bucket - Properties - Static website hosting - Edit - Enable static website hosting - Provide index document (if html page is added to S3) - Save changes

![image](https://github.com/user-attachments/assets/d71d347b-7971-41ae-bec0-65804e25dde5)
![image](https://github.com/user-attachments/assets/6e69fab2-92b1-4f45-bc33-f533e9991dd7)

- Then inside properties - Static hosting we get URL to access website.
- But here we get forbidden error as while creating bucket we've set public access to bucket as disabled as we've blocked all public access to our S3 bucket
- So go there and unckeck the box - Save changes

![image](https://github.com/user-attachments/assets/17867014-1fee-4b16-90c6-5c2760011e31)
![image](https://github.com/user-attachments/assets/fabb0f21-8e99-44bb-9a63-055b94424448)

- Now add bucket policy to access the website to allow effect

![image](https://github.com/user-attachments/assets/7c31e7fa-3826-4430-8419-4b4fab537a4d)

- Now when we try to access the website, it will be accessible
