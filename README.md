# Pushing a Docker Image to Amazon Elastic Container Registry (ECR)

Pushing a Docker image to Amazon Elastic Container Registry (ECR) involves several steps. Here’s how you can do it:

## Prerequisites
- **AWS CLI Installed**: Ensure the AWS CLI is installed and configured with the appropriate credentials.
- **Docker Installed**: Make sure Docker is installed and running on your local machine.
- **ECR Repository**: Have an existing ECR repository, or create one.

1\. Authenticate Docker to ECRRun the following command to authenticate Docker with your ECR repository:bashCopy codeaws ecr get-login-password --region | docker login --username AWS --password-stdin .dkr.ecr..amazonaws.comReplace:: Your AWS region (e.g., us-east-1).: Your AWS account ID.2. Build Your Docker ImageNavigate to the directory containing your Dockerfile and build the image:bashCopy codedocker build -t : .Example:bashCopy codedocker build -t my-app:latest .3. Tag the ImageTag the Docker image for your ECR repository:bashCopy codedocker tag : .dkr.ecr..amazonaws.com/:Example:bashCopy codedocker tag my-app:latest 123456789012.dkr.ecr.us-east-1.amazonaws.com/my-repo:latest4. Push the Image to ECRPush the image to the ECR repository:bashCopy codedocker push .dkr.ecr..amazonaws.com/:Example:bashCopy codedocker push 123456789012.dkr.ecr.us-east-1.amazonaws.com/my-repo:latest5. Verify the Image in ECRLog in to the AWS Management Console, navigate to the ECR service, and confirm the image is in your repository.
