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



![2024-07-02_10h18_56](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/61130bd1-af3e-4fef-b674-05e2b97652e9)


![2024-07-02_10h19_35](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/a7146b31-0fb5-4aab-bb10-12a1ea53c093)

![2024-07-02_10h20_22](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/f4db9698-f4c7-4ccf-87a1-d25b2ab49e09)



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


### Edit Environment Variables

![2024-07-02_10h14_48](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/88e636dc-30fa-43b7-b7a0-4634cecc9192)


### Create Another Bucket with Public Access & Upload Required Files

![2024-07-02_10h37_26](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/64a7579f-fb89-4960-9de1-6df6135d9274)

![2024-07-02_10h37_44](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/cdb21401-8770-49cd-8a45-81ef3b597dd8)


![2024-07-02_11h40_10](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/71c10425-21fd-4b57-b3a7-048448f13959)



### Generate Policy for the S3 Bucket that we have created  previous documentation

![2024-07-02_11h46_57](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/bf0012f4-7de1-4d81-886a-1ca91a8fcd69)


![2024-07-02_11h48_34](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/9e83b9d0-4ab7-41c0-891f-116f7db80c8a)


![2024-07-02_11h48_53](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/e406aba7-0aa2-4d29-8538-216fbbda70aa)


![2024-07-02_11h49_26](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/da06b982-10c7-4560-8456-131fa18ed0be)

![2024-07-02_11h51_44](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/38f3e758-2578-4235-b33d-83d1971f3bf0)


### Step 4: Deploy the Application
1. Use the AWS CLI to deploy your Lambda functions and update the S3 bucket with the latest front-end code.
2. Deploy the API Gateway and note the endpoint URLs.





### Step 5: Test the Application
1. Open your browser and navigate to the S3 bucket URL to access your web application.
2. Test the different functionalities to ensure everything is working correctly.


![2024-07-02_11h53_58](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/91ce201e-b548-4b0d-bfdc-1307b16a712e)


![2024-07-02_11h54_12](https://github.com/MdShafiurRahman0/aws-serverless-web-app/assets/113176437/2ea7cbf8-f29e-43f0-9eae-aca62ca5fefa)



### Conclusion
By following these steps, you have successfully deployed a serverless web application on AWS using IAM, DynamoDB, Lambda, SES, API Gateway, and S3. This architecture provides scalability, cost-effectiveness, and high availability, leveraging the power of AWS services.
