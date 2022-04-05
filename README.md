# DevOps-2201
AWS CLI ASSIGNMENT - 

1.1.1 Create a Bucket

aws s3 mb s3://izaan-mozam2246 --region us-west-1

Listing Bucket - 

1.1.2 Uploading one object in the created bucket

aws s3 cp --recursive data s3://izaan-mozam2246

Include and Exclude command

mozammel$ aws s3 cp --recursive data s3://izaan-mozam2246 --exclude "*" --include "private.txt"

1.1.4 Clean up
Removing the Objects from the bucket
aws s3 rm --recursive s3://izaan-mozam2246

Removing the bucket from S3
aws s3 rb s3://izaan-mozam2246

1.2.1
Make s3 bucket public using CLI with sync command - 

aws s3 sync .  s3://izaan-mozam-admin --acl public-read

After this, can you download one of your files from the bucket without using
your API credentials?

aws s3api get-object --bucket izaan-wali1317 --key test1.txt test123.txt

1.2.2 
Will make private.txt publicly unreadable - 

aws s3 cp private.txt s3://izaan-mozam-admin --acl private

Is there a way you can change the permissions on the file without re-uploading it?

aws s3api put-object-acl --bucket izaan-mozam-admin --key private.txt --acl public-read

1.2.3

Create bucket using s3api

aws s3api create-bucket --bucket izaan-mozam2246

To get ARN number using CLI - 

aws sts get-caller-identity

Create and assign an IAM policy to explicitly grant yourself
maintenance access
Set a bucket policy to grant public read access.

aws s3api put-bucket-policy --bucket izaan-mozam2246 --policy file:///Users/mozammel/IdeaProjects/DevOps-2201/policy.json
aws s3api put-bucket-policy --bucket izaan-mozam2246 --policy file://policy.json

