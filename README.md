# CI-CD-with-Docker-Compose
Project Description: Automated Java Application Deployment

Overview:
This project focuses on automating the testing, building, and deployment of a Java application along with a PostgreSQL database using Jenkins and Docker Compose. The pipeline streamlines the software development and delivery process, ensuring consistency and reliability.

Components:

Jenkins Pipeline:

Pipeline Overview:
The project utilizes a Jenkins pipeline to automate the deployment process.
The pipeline comprises three stages: test, build, and deploy.
Stages:

Stage 1: Test:

Description:
In this stage, the application undergoes testing, ensuring its functionality and quality.
Actions:
Executes a script that echoes "Testing the application..." to the console.
Stage 2: Build:

Description:
The build stage is responsible for compiling and preparing the application for deployment.
Actions:
Executes a script that echoes "Building the application..." to the console.
Stage 3: Deploy:

Description:
This stage handles the deployment of the Java application and a PostgreSQL database to a remote server (52.90.178.142).
It involves securely transferring necessary files and executing deployment commands.
Actions:
Utilizes an SSH agent (aws) for secure remote server access.
Copies docker-compose.yaml and server-cmd.sh to the remote server's home directory.
Executes the custom deployment command ${cmd} (defined as "bash ./server-cmd.sh") on the remote server.
Docker Compose Configuration (docker-compose.yaml):

Version:
The Docker Compose file is written in version '3.8'.
Services:

Service 1: java-maven-app:

Description:
This service runs a Java application using the image tushar24sharma/docker:7.1.
Ports:
Maps port 8080 on the host to port 8080 in the container, allowing access to the Java application.
Service 2: postgres:

Description:
This service runs a PostgreSQL database using the official postgres:13 image.
Ports:
Maps port 5432 on the host to port 5432 in the container, enabling external access to the PostgreSQL database.
Environment Variables:
Sets the POSTGRES_PASSWORD environment variable to 'my-pwd' to specify the password for the PostgreSQL database.
Project Goals:

Automate the software development and deployment process.
Ensure consistent and reliable testing and building of the Java application.
Deploy the Java application and PostgreSQL database to a remote server securely.
Provide a structured and automated approach to software development and delivery.
Note: Before running the pipeline and Docker Compose configuration, ensure that the required Docker images are available or can be pulled from Docker Hub, and that the SSH key associated with the aws SSH agent has appropriate access to the remote server (52.90.178.142) for successful deployment.

This project aims to simplify the deployment process of a Java application and database while maintaining security and reliability through automation and containerization.


<img width="935" alt="Screenshot 2023-09-24 at 1 58 05 AM" src="https://github.com/Tushar240503/CI-CD-with-Docker-Compose/assets/98592305/1ecb45e9-e330-4ddf-a338-5b3428b2afc0">



