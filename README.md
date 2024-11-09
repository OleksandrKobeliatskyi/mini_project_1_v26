Mini Project 1: Sports Gym Management System

This project is aimed at creating a management system for sports gyms, focusing on automating backend services using a CI/CD pipeline. It is designed to help manage the operations of sports gyms, including bookings, membership management, and other related services. The backend services are deployed to AWS EC2 using GitHub Actions. The project includes two backend components, each of which runs in a separate Docker container. These services are managed using Docker Compose and are deployed using an automated workflow.

Project Structure

The project has the following main components:

backend_rds: This directory contains the code and Dockerfile for the RDS backend.

backend_redis: This directory contains the code and Dockerfile for the Redis backend.

frontend: Frontend components (if applicable).

docker-compose.yml: A Docker Compose file used for managing multi-container deployment.

requirements.txt: Combined requirements file for both backend services.

.github/workflows/ci_cd_workflow.yml: Contains the GitHub Actions workflow configuration for CI/CD automation.

Technologies Used

GitHub Actions for CI/CD

Docker for containerization

AWS EC2 for hosting the application

Docker Compose for multi-container deployment

CI/CD Workflow

This project uses a GitHub Actions workflow to automate the CI/CD process.

Workflow Steps

Checkout the repository

The code is checked out from GitHub to the CI runner.

Build Docker Images

Build Docker images for both backend services from their respective Dockerfiles.

Deploy to AWS EC2

Copy the docker-compose.yml file to the EC2 instance.

Restart Docker containers using Docker Compose on the EC2 instance.

Trigger Events

The workflow is triggered on:

Push events to the main branch.

Pull requests to the main branch.

Prerequisites

To run this project, you will need:

AWS Account with an EC2 instance set up.

Docker installed on the EC2 instance.

An SSH key to connect to your EC2 instance.

GitHub Actions secrets for the SSH key, EC2 public IP, and any AWS credentials required.

Setting Up the Project

Clone the Repository

git clone <repository-url>

Create AWS EC2 Instance

Launch an EC2 instance and ensure Docker is installed.

Add GitHub Secrets

Add EC2_SSH_KEY with your .pem file content.

Add other necessary secrets such as AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, and EC2_PUBLIC_IP.

Push Changes to GitHub

Push your code changes to trigger the GitHub Actions workflow.

Running the Application

After pushing your changes, the GitHub Actions workflow will handle building, pushing, and deploying the Docker containers on your EC2 instance. You can verify if the containers are running by connecting to your EC2 instance via SSH and running the following command:

docker ps

Stopping the Application

To stop the running containers, connect to your EC2 instance and execute:

cd /home/ec2-user/mini_project_1_v26
docker-compose down

Troubleshooting

Permission Denied Errors: Make sure your .pem file has the correct permissions (chmod 400 <your-pem-file>).

SSH Connection Issues: Verify the EC2_PUBLIC_IP and ensure your security group allows SSH access.

Docker Errors: Ensure Docker is installed and running on your EC2 instance.

License

This project is licensed under the MIT License.

