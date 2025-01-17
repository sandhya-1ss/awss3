* AWS Lambda Function to Store Documents in S3

This is an AWS Lambda function that accepts a document or PDF file and stores it in an Amazon S3 bucket. The file is provided as base64-encoded content, and the function uploads it to the specified S3 bucket with a given file name.



This Lambda function is designed to help automate the process of storing document files (e.g., PDF, DOCX) in Amazon S3. It decodes a base64-encoded file and uploads it to a specified S3 bucket. You can integrate this Lambda function into your applications.

*Features

- Accepts file content in base64-encoded format.
- Stores the file in a specified S3 bucket.
- Supports various file types (ex PDF, DOCX).
- Provides error handling for invalid inputs and other issues.

*Prerequisites

- **AWS Account**: You will need an AWS account to use AWS Lambda and S3.
- **IAM Role**: Ensure that the Lambda function has an appropriate IAM role with permissions to read/write to your S3 bucket.
- **S3 Bucket**: Create an S3 bucket where the files will be stored.

*Step 1: Create an S3 Bucket

1. Go to the **S3 Console**.
2. Create a new S3 bucket to store the uploaded files. For example, name it 'my-documentsbucket'.

*Step 2: Create an IAM Role for Lambda

1. Go to the **IAM Console**.
2. Create a new role with **AWS Lambda** as the trusted entity.
3. Attach the 'AmazonS3FullAccess' policy to this role, allowing the Lambda function to upload files to S3.
4. Save the role name (ex-lambda-s3-role)

*Step 3: Create the Lambda Function

1. Go to the **AWS Lambda Console**.
2. Create a new Lambda function with Python as the runtime (ex Python 3.8 or 3.9).
3. Choose the IAM role you created in Step 2.
4. Paste the Lambda function code into the function editor.

*Step 4: Testing the Lambda Function
You can test the Lambda function using the AWS Lambda console:

Click on Test in the Lambda console.
Create a test event with the following sample JSON payload:
json
Copy
{
  "file_content": "base64_encoded_content_of_pdf_or_document",
  "bucket_name": "my-documentsbucket",
  "file_name": "document.pdf"



