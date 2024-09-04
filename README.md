**Implement a CI/CD Pipeline with GitHub Actions for Automated Deployment and Rollback**

Overview:
  This repository demonstrates a CI/CD pipeline using GitHub Actions to automate the deployment of a simple web application to AWS ECS (Elastic Container Service). The     pipeline includes deployment, integration tests, and rollback functionality.

Prerequisites:
  1) AWS Account with IAM User & ECS, ECR service Enabled.
  2) GitHub Account with GitHub Action.
  3) Docker & Git Installed on Local.

        *Deply On Local* 
Steps: 
  1) Clone the repository:
       git clone https

  2) Go through Directory:
       ~ cd /VE3/
     
  3) Build & Run the Docker Container:
       ~ docker build -t react-app-img . && docker run -itd --name react-app -p 80:80 react-app-img

  4) Verify the Web Applcation:
       ~ curl http://localhost:80


      *Deploy On ECS*

Steps:
  1) Push Directory(VE3) to your GitHub Repo.

  2) Add secrets in Repo setting, AWS user  access_key_id & private_access_key.
    
  3) Create Private Repository on AWS ECR.
  
  4) Create Task_definition in AWS_ECS, copy the json file to GitHub Repo.
  
  5) Create Cluster in AWS_ECS and Service in that Cluster.
  
  6) Goto GitHub Repo, then Actions.
  
  7) Make changes in .github/workflows/main.yml accordingly.
  
  8) Edit region, repository, cluster, service,

  9) Commit the changes.
  
  10) Now verify your REACT_App on Browser with Public_IP.

    Note: Make sure port 80 is open in security_group.


**GitHub Actions Workflow**

The GitHub Actions workflow is defined in the .github/workflows/main.yml file. 
The workflow consists of five jobs:

  *Checkout:* 
    Checkout the code from the GitHub repository.
  
  *Build-and-push:*
    Build and push the Docker image to ECR.
    
  *Login:*
    Login in AWS_ECR with user credentials.

  *Build & tag:*
    Docker build image with special tag to push on AWS_ECR.

  *Task_def:*
    Update Task definition with latest Docker Image.
    
  *Deploy:*
    Deploy the Docker image to ECS.
  
  *Integration-tests:*
    Perform integration tests on the deployed application.
  
  *Rollback:*
    Rollback the deployment if the integration tests fail.



    The End !





   Happy Learning :)
    
