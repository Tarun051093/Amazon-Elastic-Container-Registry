# Pushing a Docker Image to Amazon Elastic Container Registry (ECR)

Pushing a Docker image to Amazon Elastic Container Registry (ECR) involves several steps. Here’s how you can do it:

## Prerequisites
- **AWS CLI Installed**: Ensure the AWS CLI is installed and configured with the appropriate credentials.
- **Docker Installed**: Make sure Docker is installed and running on your local machine.
- **ECR Repository**: Have an existing ECR repository, or create one.

# Steps to Push a Docker Image to Amazon ECR

## 1. Authenticate Docker to ECR
Run the following command to authenticate Docker with your ECR repository:  

aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com

Replace:

<region>: Your AWS region (e.g., us-east-1).
<aws_account_id>: Your AWS account ID.
## 2. Build Your Docker Image
Navigate to the directory containing your Dockerfile and build the image:


Copy code
docker build -t <image_name>:<tag> .
Example:


Copy code
docker build -t my-app:latest .
