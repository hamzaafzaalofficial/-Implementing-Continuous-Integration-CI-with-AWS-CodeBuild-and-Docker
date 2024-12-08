# -Implementing-Continuous-Integration-CI-with-AWS-CodeBuild-and-Docker

Objective
The objective of the "Implementing Continuous Integration with AWS CodeBuild and Docker" is to establish a streamlined and automated process for building, testing, and validating software applications whenever changes are made to the source code. This is achieved by integrating AWS CodeBuild with Docker.


# Step 1: Set Up Your AWS Environment
Login to AWS console & go into ECR and create a registry/repository there.
Notice the push commands for the repo you created, and we will be using them in our buildspec.yaml file, replace your values for REPOSITORY_URI & aws ecr get-login-password 
Create an AWS CodeBuild project in the AWS Management Console.
Specify your source code repository and branch like GitHub.
Choose the build environment (e.g., Ubuntu).



# Step 2: Create a Build Specification File
Create a buildspec.yml file in your source code repository.
Define build phases such as install, build, and post_build.
Specify commands to build and test your Dockerized application


# Step 3: Configure Your Source Code Repository
Set up webhooks or triggers in your source code repository (e.g., GitHub webhook) to notify AWS CodeBuild when code changes are pushed.
Provide the webhook URL or trigger details in your source code repository settings.
Note the Role name from this page.
Go to IAM user and give permissions to the role name that you noted above. AmazonEC2ContainerRegistryFullAccess & AmazonEC2ContainerRegistryPowerUser



# Step 4: Build and Test Your Application
Whenever changes are pushed to your source code repository, AWS CodeBuild will automatically trigger a build using thebuildspec.ymlfile. AWS CodeBuild will create a Docker build environment based on the specified image and execute the build commands. Your application will be built and tested within the Docker environment.

