# Aws-s3-bucket-file-upload-public-access-configaration
# AWS S3 Bucket Creation and File Upload

## Project Overview

This project demonstrates how to create an Amazon S3 bucket, upload files, and configure public access permissions using a bucket policy.

## Services Used

* Amazon S3
* AWS Management Console

## Region

* Asia Pacific (Mumbai) - ap-south-1

## Objectives

* Create an S3 bucket
* Upload files to the bucket
* Configure public access permissions
* Resolve "Access Denied (403 Forbidden)" errors

## Steps Performed

### 1. Create an S3 Bucket

* Logged in to the AWS Management Console
* Opened the Amazon S3 service
* Created a bucket named `srikanth-s3demo-bucket`
* Selected the Mumbai region (`ap-south-1`)

### 2. Upload a File

* Opened the bucket
* Uploaded the file `pspk.jpg`
* Verified successful upload

### 3. Resolve Access Denied Error

Initially, the uploaded image was not accessible publicly because Amazon S3 blocks public access by default.

### 4. Enable Public Access

* Opened the bucket Permissions tab
* Edited Block Public Access settings
* Disabled the required restrictions
* Saved the changes

### 5. Configure Bucket Policy

Added the following bucket policy to allow public read access to objects:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::srikanth-s3demo-bucket/*"
    }
  ]
}
```

## Outcome

* Successfully created an S3 bucket
* Uploaded image files
* Configured public access using a bucket policy
* Accessed the uploaded image through its S3 Object URL

## Learning Outcomes

* Understanding Amazon S3 Object Storage
* Managing S3 Bucket Permissions
* Configuring Bucket Policies
* Troubleshooting Access Denied (403) Errors
