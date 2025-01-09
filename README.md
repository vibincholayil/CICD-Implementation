This project is a end-to-end CI/CD pipeline implementation in Jenkins for a Java-based application, leveraging Maven, SonarQube, Argo CD, Helm, and Kubernetes. This project helped me to gain knowledge about Installation,  configuration and end to end pipeline implementation.<br>

I divided this project into two parts:<br>
<b>Continuous Integration</b> – The Java application was built with Maven, and static code analysis was performed using SonarQube. Then, the Docker image was built and pushed to Docker Hub.<br>
<b>Continuous Delivery</b> – I applied a GitOps approach. For this, I created a manifest repository in the source code repository and automatically updated it with a shell script. Using ArgoCD, I deployed the manifest automatically to the Kubernetes clusters.