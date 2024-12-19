# Pushing a Docker Image to Amazon Elastic Container Registry (ECR)

Pushing a Docker image to Amazon Elastic Container Registry (ECR) involves several steps. Here’s how you can do it:

## Prerequisites
- **AWS CLI Installed**: Ensure the AWS CLI is installed and configured with the appropriate credentials.
- **Docker Installed**: Make sure Docker is installed and running on your local machine.
- **ECR Repository**: Have an existing ECR repository, or create one.

# Steps to Push a Docker Image to Amazon ECR

# Steps to Push a Docker Image to Amazon ECR

## 1. Authenticate Docker to ECR
Run the following command to authenticate Docker with your ECR repository:


aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com


## 3. Tag the Image
Tag the Docker image for your ECR repository:


docker tag <image_name>:<tag> <aws_account_id>.dkr.ecr.<region>.amazonaws.com/<repository_name>:<tag>
