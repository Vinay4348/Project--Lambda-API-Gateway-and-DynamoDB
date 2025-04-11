# Project Title: Serverless Web Form with AWS Lambda, API Gateway, and DynamoDB
#Project Description:
This project demonstrates a serverless architecture built on AWS to handle user-submitted form data via a web interface.It leverages API Gateway, AWS Lambda, S3, IAM, and DynamoDB for a lightweight, scalable, and cost-effective solution.


# Architecture
![Architecture Diagram](https://github.com/Vinay4348/Project--Lambda-API-Gateway-and-DynamoDB/blob/master/Architecture.png)


# Step 1: Create IAM Role for AWS Lambda

Create a new IAM role for Lambda.

Attach the following permissions:

AWSLambdaBasicExecutionRole – for basic Lambda logging and execution.

AmazonDynamoDBFullAccess – to allow full access to DynamoDB.

AmazonS3FullAccess – to allow full access to Amazon S3.


# Step 2: Create an S3 Bucket and Upload Files

Create a new S3 bucket.

Upload the provided files in .zip format to the bucket.


# Step 3: Create a Lambda Function

Create a new Lambda function with Python 3.9 as the runtime.

Choose the previously created IAM execution role during setup.


# Step 4: Upload Code to Lambda from S3

In the Lambda function, upload the .zip file from the S3 bucket as the source code.


# Step 5: Create a DynamoDB Table

Create a DynamoDB table with the same name as specified in the Lambda function code.

Use email as the partition key (also known as the primary key).


# Step 6: Create an API Gateway

Create a new API Gateway.

Set up a REST API and configure the endpoint type as Regional.

Create both GET and POST methods for the API.

For each method, configure the integration to use the Lambda function ARN.

Ensure that Lambda Proxy Integration is enabled for both methods.

After configuring the methods, deploy the API to a new stage, and name the stage dev


# Step 7: Test the API Gateway

After creating the API Gateway and deploying it, select the Invoke URL of the API.

Open the URL in your browser and verify that the webpage is displayed correctly, confirming that the Lambda function is being triggered successfully.


# Step 8: Submit Multiple Forms

Fill in the required information on the displayed webpage for each form.

Submit the forms one by one.


# Step 9: Verify Entries in DynamoDB

Go to the DynamoDB table that was created.

Explore the table and refresh it.

Verify that the information submitted through the form is stored in the backend DynamoDB table.


# Step 10: Set Up a Custom Domain (Optional)

If you want to use a custom domain name for the API Gateway, create a new domain name in API Gateway.

Associate the domain with an SSL certificate for secure communication.

Use Amazon Route 53 to map the custom domain name to the API Gateway.












