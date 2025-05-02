# AWS-Event-Driven-Architecture-Lab
A basic hands-on lab demonstrating event-driven architecture on AWS using S3, Lambda, and SNS.

This project showcases a basic event-driven architecture on AWS. When a user uploads an image to an S3 bucket, it triggers a Lambda function using an S3 object-created event. The Lambda function acts as an event processor and publishes a message to an Amazon SNS topic. Subscribers to the SNS topic (I used email in this example) are then notified of the event. This architecture is commonly used in modern cloud applications to enable decoupled, scalable, and reactive systems.

## Flow

1. A user uploads an image to an S3 bucket.
2. This triggers a Lambda function.
3. The Lambda function processes the event and publishes a message to an SNS topic.
4. SNS sends a notification to all its subscriber(s).

   
   ![image](https://github.com/user-attachments/assets/32759a7d-56f0-4aea-bdbf-92199b32ddcf)


## Tools Used

- Amazon S3 bucket – for storing uploaded images.
- AWS Lambda – to process S3 events.
- Amazon SNS – to send notifications to subscribers.
- IAM Roles/Policies – for permissions and access control.

## Steps to Build the Project

Step 1: Create an S3 Bucket
- Bucket Name: event-driven-S3

Step 2: Create an SNS Topic
- Topic Name: ImageNotification

Step 3: Create a Subscription
- Subscribe an email address (or other supported protocol) to the 'ImageNotification' topic.

Step 4: Create a Lambda Function
- Function Name: Event-Processor
- Runtime: Python 3.x

Step 5: Write and Deploy Lambda Function Code  
- Use the provided code (remember to update the SNS Topic ARN).  
- Under Configuration > Permissions, attach the following policies:  
  - AmazonS3FullAccess  
  - AmazonSNSFullAccess
    
Step 6: Test the System  
- Upload an image to the S3 bucket.  
- You should receive an email notification with the image information as per defined in the code.

  



