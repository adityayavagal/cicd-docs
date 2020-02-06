# CICD pipeline with bitbucket

## Tools used

* Bitbucket
* AWS S3 storage bucket
* AWS CodeDeploy
* Amazon EC2

## Steps

1. Create an IAM Group, User, Role.
2. Create an S3 Bucket and an EC2 Instance (For EC2 Select the IAM role you created).
3. Create a CodeDeploy Application.
4. Create the deployment pipeline.

## Process

Developer --> Bitbucket --> AWS S3 --> AWS CodeDeploy --> AWS EC2

## Advantages

* Almost zero management effort.
* All builds are run on Docker image or a image of your choice.
* Auto scaling.

## Disadvantages

* Less flexible or you can't a lot of control on build process.
* Very less integrations are available.
* Can't run on a VM.
* Limited build time.

## Pricing

It is based on number of users and how many build minutes you want.
