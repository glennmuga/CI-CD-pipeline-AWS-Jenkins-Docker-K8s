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


Solution:
We will create 3 instances,
1 Git Client server
1 Jenkins server
1 tomcat server in the beginning
Choose t2. medium instance type for Jenkins since it requires 2 core cpu




Solution:


We will create 3 instances, 1 Git Client server
1 Jenkins server
1 tomcat server in the beginning
Choose t2. medium instance type for Jenkins since it requires 2 core cpu







Add Security group rules as suggested below




Connect the instances with the terminal


Initialize Git repository , ssh-keygen to connect the git client machine with the git repository.

The files are successfully pushed in the git repository.


Add ssh key to github repo to create a link between the github termial and web server








Add the git repo to your terminal









Install Jenkins on your Jenkins terminal



Open the Jenkins server using the public ip of the instance


You can see we have now entered the Jenkins dashboard



Create API token in Jenkins



To connect Jenkins with GitHub repository we need to add Webhooks


After adding the following we can build Jenkins and test the build is successful.



Now we will install maven on our server :



In Jenkins> dashboard > manage Jenkins > available plugins > maven integration >install


In installed plugins > type github > disable github branch source plugin and enable github plugin.


After installing restart Jenkins
In Manage Jenkins add tools and paste the java and maven path from Jenkins-server









You can now build maven and see the successful build below , we have received our git repo modules as seen below


The webapp .war file is visible which indicates that maven is building artifacts successfully.




Now we will build Apache tomcat server


Download the tomcat using wget command

Open tomcat using the public ip


Add user’s admin, deployer and assign roles using vim tomcat-users.xml


Shutdown and start the tomcat


Now open the Apache tomcat server





Expose the web application on tomcat using public Ip on 8080 Port











Create global credentials for tomcat server in Jenkins machine To integrate tomat server with Jenkins:
Go to Manage Jenkins > plugin > available plugins > deploy to container > install Manage Jenkins > Credentials > system > global credentials > add
Username: deployer Password: deployer












Docker server
Launch docker server

Install docker and start the service



Do SSH-KEYGEN to connect the server with docker server




Configure AWS


Copy public Ip address of Jenkins in docker Copy public Ip of Jenkins, docker in Jenkins


Now we can ping the terminals of each other and check the terminals are connecte











Add ssh server of Jenkins and docker in Jenkins dashboard to connect terminal to jenkins









From post build actions select build artifacts over ssh
we are connecting Jenkins with docker by providing docker IP

The commands for creating the image and pushing image into ECR





Build again and see build is successful


Image is successfully pushed into ECR





Kubernetes cluster
Launch the Kubernetes server

Attach the role to the Kubernetes instance with the access to permissions of eks, elasticcontairregistry and iam full access.



Configure AWS

Aws user has been configured here through access key and secret key generated in the Aws console.
Install EKSCTL and KUBECTL
Create EKS cluster with a name, region, subnets and without nodes.


Create node group


Create a deployment file

Create a service file


Apply the both files
Kubectl apply -f deployment.yaml Kubectl apply -f service.yaml
Check the deployment and services



Copy ssh public keys of Jenkins into Kubernetes and Kubernetes into Jenkins





Add Kubernetes server into Jenkins


Add build artifacts

Now build the job


Expose application using external Ip address It is successfully deployed and running



In this way we have automated the whole process. If there are any modifications in the jsp file from github jenkins will automatically build the project and the changes will be reflected on the live webpage automatically.
If there are any errors in the modification the build will be failed and the webpage will not be updated. It will show the last successful built which will help in preventing our webpage from crashing.


By- Glenn Muga.

