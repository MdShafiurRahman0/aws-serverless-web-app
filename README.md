# AWS Serverless web Application



## Description:

This project is a serverless web application deployed on AWS, utilizing a variety of services to achieve a scalable, cost-effective, and highly available solution. The application leverages AWS Lambda for backend processing, DynamoDB for data storage, SES for sending emails, API Gateway for API management, and S3 for static website hosting and file storage. IAM is used to manage access and permissions.



## Serverless Architecture Design & High Level Technical Overview:


![2024-07-02_11h53_13](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/33a13699-671e-47d9-9ffb-704b8eda796d)



![2024-07-01_20h30_50](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/3d736903-ca22-4fdb-a533-106c135ae852)



## Steps :


![2024-07-01_22h25_58](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/8ce59530-9aff-41a6-a4dc-c2fcffb9d583)



### Step 1:

#### 1.1 Create an S3 Bucket
1. Log in to the AWS Management Console.
2. Navigate to S3 and create a new bucket.
3. Configure the bucket to host a static website.
4. Upload your static web files (HTML, CSS, JavaScript) to the bucket.

![2024-07-01_22h33_57](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/38a9625a-a04c-496d-aa25-fa6ac64cab11)


#### 1.2 Create a DynamoDB Table
1. Navigate to DynamoDB in the AWS Management Console.
2. Create a new table with a primary key.
3. Note the table name for later use.

![2024-07-01_22h39_29](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/963a5fae-6c4d-4605-88de-d2f2dcbd24b7)


#### Copy the arn link

![2024-07-02_09h50_42](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/c70560f7-4496-43dd-9f69-1bdccb15c466)


#### 1.3 Set Up AWS Lambda
1. Navigate to Lambda in the AWS Management Console.
2. Create a new Lambda function.
3. Choose a runtime (e.g., Node.js).
4. Write or upload your Lambda function code.
5. Set up the necessary environment variables and configurations.

![2024-07-02_10h00_28](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/d9363ec3-acb3-4931-b31f-51d7f5fd0b59)


![2024-07-02_10h00_58](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/24df6c56-9d9f-4479-a84f-09f8a1ad4c25)


#### Paste the Lambda.py 


![2024-07-02_10h04_46](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/b83eb412-793a-4f5a-81d0-27b62131d5aa)



#### 1.4 Configure AWS SES
1. Navigate to Simple Email Service (SES) in the AWS Management Console.
2. Verify an email address or domain.
3. Create an IAM role for SES with the necessary permissions.


![2024-07-02_05h32_18](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/df73dbf1-67cf-4ff4-bb43-735fd3c1a012)



#### 1.5 Set Up API Gateway
1. Navigate to API Gateway in the AWS Management Console.
2. Create a new API.
3. Define the methods and resources for your API.
4. Integrate the API with your Lambda functions.

### Step 2: Set Up IAM Roles and Policies
1. Create an IAM role for Lambda with the necessary permissions for accessing DynamoDB, SES, and other AWS services.
2. Attach the appropriate policies to the IAM roles.


![2024-07-02_09h54_19](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/bd2996fc-a424-43fe-9a5c-a1589712738e)


![2024-07-02_09h55_23](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/482f5dd3-a18d-4281-956a-4e1e8dbb566a)


![2024-07-02_09h55_56](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/5c16ff00-0a42-4927-9784-21dcdefe05b4)


![2024-07-02_09h57_09](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/db97f68f-ba24-4457-bbf6-b90b83a6573c)



### Step 2: Paste the arn link the json code

 ![2024-07-02_09h50_54](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/f205c496-81f8-42ab-bfff-f6f902173985)


### Step 3: Develop the Application
1. Write the front-end code and upload it to the S3 bucket.
2. Write the back-end code for Lambda functions to handle requests and interact with DynamoDB and SES.
3. Define the API endpoints in API Gateway and link them to the corresponding Lambda functions.

### Step 4: Deploy the Application
1. Use the AWS CLI to deploy your Lambda functions and update the S3 bucket with the latest front-end code.
2. Deploy the API Gateway and note the endpoint URLs.

### Step 5: Set Up CI/CD with GitHub
1. Create a new repository on GitHub.
2. Push your application code to the repository.
3. Set up a GitHub Actions workflow to automate the deployment process.

#### Sample GitHub Actions Workflow
```yaml
name: Deploy to AWS

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'

      - name: Install dependencies
        run: npm install

      - name: Deploy to S3
        run: aws s3 sync ./frontend s3://your-s3-bucket-name --delete

      - name: Deploy Lambda function
        run: |
          zip -r lambda.zip ./backend
          aws lambda update-function-code --function-name your-lambda-function-name --zip-file fileb://lambda.zip

      - name: Deploy API Gateway
        run: aws apigatewayv2 update-api --api-id your-api-id --deployment-id your-deployment-id
```

### Step 6: Test the Application
1. Open your browser and navigate to the S3 bucket URL to access your web application.
2. Test the different functionalities to ensure everything is working correctly.

### Conclusion
By following these steps, you have successfully deployed a serverless web application on AWS using IAM, DynamoDB, Lambda, SES, API Gateway, and S3. This architecture provides scalability, cost-effectiveness, and high availability, leveraging the power of AWS services.

---

This guide should help you set up and deploy your serverless web application on AWS efficiently. If you have any specific questions or need further assistance, feel free to ask!
