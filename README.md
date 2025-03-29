# CI-CD-pipeline-AWS-Jenkins-Docker-K8s
This is a complete pipepline created to deploy a JAVA Application using variious devops tools 

📌 Problem Statement
Create an end-to-end CI/CD pipeline in AWS platform using Jenkins as the orchestration tool, Github as the SCM, Maven as the Build tool, deploy in a docker instance and create a Docker image, Store the docker image in ECR, Achieve Kubernetes deployment using the ECR image. Build a sample java web app using maven.


Requirements
✔️ CI/CD pipeline System

✔️ Git - Local version control system.

✔️ GitHub - Distributed version control system.

✔️ Jenkins - Continuous Integration tool.

✔️ Maven - Build tool.

✔️ Docker - Containerization.

✔️ Kubernetes - Container management tool.


Step-1:
➢ Setup CI/CD with GitHub, Jenkins, Maven & Tomcat.
➢ Setup Jenkins
➢ Setup & Configure Maven, Git.
➢ Setup Tomcat Server.
➢ Integrating GitHub, Maven, Tomcat Server with Jenkins.
➢ Create a CI and CD Job.
➢ Test the Deployment

Step-2:
➢ Setup CI/CD with GitHub, Jenkins, Maven & Docker.
➢ Setting up the docker Environment.
➢ Create an Image and Container on Docker Host.
➢ Integrate Docker Host with Jenkins.
➢ Create CI/CD Job on Jenkins to build and deploy on container.

Step-3:
➢ Build and Deploy on Container. ➢ CI/CD with GitHub, Jenkins, Maven & Kubernetes.
➢ Setting up the Kubernetes (EKS).
➢ Write pod service and deployment manifest file.
➢ CI/CD Job to build code on Jenkins & Deploy it on Kubernetes.

Step-4:
➢ Deploy artifacts on the Kubernetes
➢ Write codes in the artifacts of docker and Kubernetes which we want to run.
➢ Now build the code in Jenkins.
➢ Check in Kubernetes the pods are getting created or not.
➢ Now copy the service IP and paste it in the browser and check the output.
