# Securing Data in AWS S3 Buckets

## Introduction

In this project, you'll learn how to secure data in AWS S3 buckets. S3 is a scalable storage service, and securing your data is crucial. We'll cover creating S3 buckets, setting bucket policies, enabling encryption, and implementing best practices for securing your S3 data.

## Pre-requisites

- Basic understanding of cloud computing
- An AWS account (free tier available)
- Basic knowledge of command-line interface (CLI)

## Lab Set-up and Tools

1. **AWS Account**: Sign up for a free AWS account if you don't have one.
2. **AWS Management Console**: Access to the AWS Management Console.
3. **AWS CLI**: Install the AWS Command Line Interface (CLI) on your local machine.

## Exercises

### Exercise 1: Create an S3 Bucket

#### Steps

1. Log in to the [AWS Management Console](https://aws.amazon.com/console/).
2. Navigate to the S3 Dashboard.
3. Click on "Create bucket".
4. Configure the bucket settings:
    - Bucket name: `my-secure-bucket`
    - Region: Select a region
    - Block all public access: Enable
5. Click "Create bucket".

#### Expected Output

- An S3 bucket `my-secure-bucket` created with public access blocked.

### Exercise 2: Enable Bucket Versioning

#### Steps

1. Navigate to the S3 Dashboard.
2. Select the bucket `my-secure-bucket`.
3. Click on "Properties".
4. Scroll down to "Bucket Versioning" and click "Edit".
5. Enable versioning and save changes.

#### Expected Output

- Versioning enabled for the S3 bucket `my-secure-bucket`.

### Exercise 3: Enable Server-Side Encryption

#### Steps

1. Navigate to the S3 Dashboard.
2. Select the bucket `my-secure-bucket`.
3. Click on "Properties".
4. Scroll down to "Default encryption" and click "Edit".
5. Enable server-side encryption with AWS-KMS.
6. Choose a KMS key or create a new one.
7. Save changes.

#### Expected Output

- Server-side encryption enabled for the S3 bucket `my-secure-bucket`.

### Exercise 4: Set Bucket Policies

#### Steps

1. Navigate to the S3 Dashboard.
2. Select the bucket `my-secure-bucket`.
3. Click on "Permissions".
4. Scroll down to "Bucket policy" and click "Edit".
5. Add the following policy to allow read access for a specific user:
    ```json
    {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Effect": "Allow",
          "Principal": {
            "AWS": "arn:aws:iam::123456789012:user/username"
          },
          "Action": "s3:GetObject",
          "Resource": "arn:aws:s3:::my-secure-bucket/*"
        }
      ]
    }
    ```
6. Save changes.

#### Expected Output

- Bucket policy added to allow specific user access to the S3 bucket `my-secure-bucket`.

### Exercise 5: Configure S3 Access Logs

#### Steps

1. Navigate to the S3 Dashboard.
2. Select the bucket `my-secure-bucket`.
3. Click on "Properties".
4. Scroll down to "Server access logging" and click "Edit".
5. Enable access logging and specify a target bucket for logs (e.g., `my-log-bucket`).
6. Save changes.

#### Expected Output

- Server access logging enabled for the S3 bucket `my-secure-bucket`.

## Conclusion

By completing these exercises, you have successfully created an S3 bucket, enabled versioning and server-side encryption, set bucket policies, and configured access logs. These steps are essential for securing data stored in AWS S3.
