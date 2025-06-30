# AWS S3 and Lambda Integration

This project demonstrates the integration of **Amazon S3** with **AWS Lambda** to automate the response to file uploads. It showcases an event-driven serverless architecture on AWS.

## 📌 Project Overview

Whenever a file is uploaded to an S3 bucket, a Lambda function is triggered. This function logs the upload event, providing real-time automation without any manual intervention.

---

## 🚀 Services Used

- **Amazon S3**  
  Scalable object storage used to store uploaded files and trigger events.

- **AWS Lambda**  
  Serverless compute service that runs Python code in response to S3 events.

---

## 🔧 Implementation Steps

1. **Created S3 Bucket**  
   - Bucket name: `rahulcloud-mys3`

2. **Created Lambda Function**  
   - Function name: `rahulcloud-mylamb`  
   - Runtime: Python 3.13  
   - Function logs upload events.

3. **Configured S3 Trigger**  
   - Event: `PUT` (i.e., when a new file is uploaded)  
   - Connected the S3 bucket to trigger the Lambda function.

4. **Tested Upload**  
   - Uploaded an image to the S3 bucket.

5. **Verified Execution**  
   - Confirmed Lambda function ran by checking logs in **CloudWatch**.

---

## 📋 Output Summary

The Lambda function was successfully triggered upon file upload. Logs confirmed the execution and displayed the expected message from the Lambda code.

---

## ✅ Conclusion

This project provides a simple but powerful example of event-driven architecture using AWS services. It’s ideal for beginners to understand:

- **S3 bucket events**
- **Lambda function triggers**
- **Serverless workflow automation**
---

## 🚀 Deployment Instructions

To deploy this project on your AWS account:

1. **Create an S3 Bucket**
   - Go to the S3 console.
   - Create a bucket named `rahulcloud-mys3` (or any name you prefer).

2. **Create a Lambda Function**
   - Go to the Lambda console.
   - Create a new function named `rahulcloud-mylamb`.
   - Choose Python 3.13 as the runtime.

3. **Add the Lambda Code**
   ```python
   import json

   def lambda_handler(event, context):
       print("File uploaded to S3 bucket!")
       print("Event received:", json.dumps(event))
       return {
           'statusCode': 200,
           'body': json.dumps('Lambda function executed successfully!')
       }
   ```

4. **Set S3 Trigger**
   - Under the Lambda function configuration, add a trigger.
   - Choose S3, select your bucket, and set the event type to `PUT`.

5. **Upload a File**
   - Upload any file (e.g., image) to the bucket using the AWS Console or CLI.

6. **Verify Execution**
   - Go to CloudWatch Logs.
   - Check the logs for the Lambda function execution.

---

## 💡 Tip

You can also automate this entire setup using AWS CloudFormation or Terraform for infrastructure as code.

