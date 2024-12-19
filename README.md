# Elastic Container Registry
Pushing a Docker image to Amazon Elastic Container Registry (ECR) involves several steps. Here’s how you can do it:

**Prerequisites:**
AWS CLI Installed: Ensure the AWS CLI is installed and configured with the appropriate credentials.
Docker Installed: Make sure Docker is installed and running on your local machine.
ECR Repository: Have an existing ECR repository, or create one.
Steps:
1. Authenticate Docker to ECR
Run the following command to authenticate Docker with your ECR repository:

bash
Copy code
aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com
Replace:

<region>: Your AWS region (e.g., us-east-1).
<aws_account_id>: Your AWS account ID.
2. Build Your Docker Image
Navigate to the directory containing your Dockerfile and build the image:

bash
Copy code
docker build -t <image_name>:<tag> .
Example:

bash
Copy code
docker build -t my-app:latest .
3. Tag the Image
Tag the Docker image for your ECR repository:

bash
Copy code
docker tag <image_name>:<tag> <aws_account_id>.dkr.ecr.<region>.amazonaws.com/<repository_name>:<tag>
Example:

bash
Copy code
docker tag my-app:latest 123456789012.dkr.ecr.us-east-1.amazonaws.com/my-repo:latest
4. Push the Image to ECR
Push the image to the ECR repository:

bash
Copy code
docker push <aws_account_id>.dkr.ecr.<region>.amazonaws.com/<repository_name>:<tag>
Example:

bash
Copy code
docker push 123456789012.dkr.ecr.us-east-1.amazonaws.com/my-repo:latest
5. Verify the Image in ECR
Log in to the AWS Management Console, navigate to the ECR service, and confirm the image is in your repository.
