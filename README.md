<H1>CICD-Implementation</H1>
<p>This project is a end-to-end CI/CD pipeline implementation in Jenkins for a Java-based application, leveraging Maven, SonarQube, Argo CD, Helm, and Kubernetes. This project helped me to gain knowledge about Installation,  configuration and end to end pipeline implementation.</p>

I divided this project into two parts:<br>
<b>Continuous Integration</b> – The Java application was built with Maven, and static code analysis was performed using SonarQube. Then, the Docker image was built and pushed to Docker Hub.<br>
<b>Continuous Delivery</b> – I applied a GitOps approach. For this, I created a manifest repository in the source code repository and automatically updated it with a shell script. Using ArgoCD, I deployed the manifest automatically to the Kubernetes cluster.<br>
    
I installed all necessary dependencies, including Maven.<br>
Then, I created a Docker image named cicd-pipeline using the base image openjdk:11. I ran the image locally and exposed it on localhost:8010 using the following commands:<br>

Build the Docker image<br><i>docker build -t vibincholayil/cicd-pipeline:v1 .</i>

Run the Docker container and map port 8010 to 8080<br><i>docker run -d -p 8010:8080 -t vibincholayil/cicd-pipeline:v1</i>

The application ran successfully on my localhost

![Alt Text](assets/image1.png)

<h2>Project Start: Below, I explain how to run this in a CI/CD pipeline.</h2>

<b>Creating an EC2 Instance</b><br>
<p>I have set up an EC2 instance with the instance type t2.large, running the Ubuntu operating system. This configuration is chosen to ensure sufficient storage and resources for managing the demanding configurations required for this project.</p>

<p>Then, i have SSH-ed into the AWS server, updated the Ubuntu operating system, and installed Jenkins on it. Additionally, I installed the 'Docker Pipeline' and 'SonarQube Scanner' plugins in Jenkins.</p>

![alt text](image-5.png)<br>
![alt text](image-6.png)

<p>Started SonarQube and connected it to Jenkins using a Sonar token.</p>

![alt text](image-7.png)

<p>Then,i installed Docker and granted both the Jenkins user and the Ubuntu user the necessary permissions to access the Docker daemon. After completing all the Jenkins configurations, I restarted the Jenkins service for the first time to apply the changes.</p>

<p>After that Install Kubernetes and ArgoCD</p>
<p>After that, I installed Kubernetes and ArgoCD, using the installation links provided on OperatorHub for setting up ArgoCD.</p>


