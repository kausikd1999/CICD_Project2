DevOps CI/CD Pipeline Project

Overview
	•	Welcome to the CI/CD (Continuous Integration/Continuous Deployment) project powered by GitHub, Jenkins, Docker, Kubernetes, and more. This project aims to streamline the development, testing, and deployment processes of applications using modern DevOps practices. By leveraging containerization, orchestration, and monitoring tools, we ensure efficient delivery and operational excellence.

 Key Technologies Used:
	•	GitHub: Hosts the source code repository and manages version control.
	•	Jenkins: Orchestrates the CI/CD pipelines, automating builds, tests, and deployments.
	•	Docker: Provides containerization for consistent and reproducible environments.
	•	Kubernetes: Manages containerized applications, ensuring scalability and resilience.
	•	SonarQube: Ensures code quality through static code analysis.
	•	Nexus: Acts as an artifact repository for storing and managing build artifacts.
	•	Prometheus: Monitors and collects metrics from applications and infrastructure.
	•	Grafana: Visualizes metrics collected by Prometheus, enabling effective monitoring.

 Features:
	•	Automated Builds: Triggered on code commits to GitHub, Jenkins automates the build process, ensuring consistent and reliable builds.
	•	Continuous Deployment: Deploy Dockerized applications to Kubernetes clusters, facilitating rapid and controlled deployments.
	•	Monitoring and Metrics: Utilize Prometheus and Grafana to monitor application performance, track metrics, and set up alerts for proactive management.

 Purpose:
	•	This project aims to enhance development agility and operational efficiency by integrating robust CI/CD pipelines with Kubernetes orchestration and comprehensive monitoring. It enables teams to iterate faster, maintain high code quality, and deliver reliable applications to production seamlessly.

Prerequisites
	•	GitHub 
	•	Jenkins
	•	Docker
	•	K8s Cluster
	•	SonarQube
	•	Nexus
	•	Prometheus
	•	Grafana

 Procedure
1. Push code to Github

2. Setting Up Jenkins on AWS
Installing Jenkins
Deploy Jenkins on AWS EC2 instance:
	•	Launch an EC2 instance with Amazon Linux or Ubuntu.
	•	Connect to your EC2 instance using SSH.
Configuring Jenkins
	•	Install Jenkins on your EC2 instance using the official installation guide.
	•	Access Jenkins at http://my-ec2-public-ip:8080 in your web browser.
	•	Follow the setup wizard to complete the installation.
	•	Install necessary plugins such as Git, Docker, Kubernetes, etc., from the Jenkins dashboard.
Install Docker on your AWS EC2 instance:
	•	SSH into your EC2 instance.
	•	Followed Docker's official installation guide for Amazon Linux or Ubuntu.

3. Setting Up Kubernetes on AWS
Installing Kubernetes (EKS)
Set up a Kubernetes cluster using Amazon EKS:
        •       Create IAM user.
        •       Assign all the needed policies in order to create EKS cluster.   
	•	Access the instance and install CLI like AWSCLI, KUBECTL, EKSCTL.
	•	Create cluster by eksctl & use iam-oidc-provider to get/assume IAM roles.
	•	With eksctl create how many worker nodes needed and set other conditions.

4. Setting Up SonarQube on AWS
Installing SonarQube
Deploy SonarQube on AWS EC2 instance using Docker:
	•	Launch an EC2 instance for SonarQube.
Install Docker on your AWS EC2 instance:
	•	SSH into your EC2 instance.
	•	Followed Docker's official installation guide for Amazon Linux or Ubuntu.
	•	Install SonarQube using official installation instructions.
	•	Setup SonarQube Container and run.
Install Trivy:
	•	Follow Trivy File System Scanner Documentaion.

5. Setting Up Nexus Repository Manager on AWS
Installing Nexus
Deploy Nexus Repository Manager on AWS EC2 instance:
	•	Launch an EC2 instance for Nexus.
Install Docker on your AWS EC2 instance:
	•	SSH into your EC2 instance.
	•	Followed Docker's official installation guide for Amazon Linux or Ubuntu.
	•	Install Nexus using official installation instructions.
	•	Setup Nexus Container and run.

6. CI/CD Pipeline
Start this step after all the housekeeping in Jenkins
Stages to be mentioned in Pipeline:
	•	Git Checkout
	•	Compile
	•	Test
	•	Trivy Scan File System
	•	SonarQube Analysis
	•	Build
	•	Deploy Artifacts to Nexus
	•	Build & Tag Docker Image
	•	Trivy Scan Image
	•	Publish Docker Image
	•	Deploy to k8s
	•	Verify Deployment

7. RBAC Setup in EKS Cluster & Continuous Deployment to K8s:
	•	Create Service Account
	•	create new namespace
	•	Create a yml file to assign role & resource 
	•	Assign this role to service account and bind this role to service account
	•	Create a yml file for authentication & apply it and retrieve the token
	•	add credential to Jenkins and that will be used in pipeline to deploy to k8s.

6. Setting Up Prometheus, Blackbox exporter, Node exporter and Grafana on AWS for Monitoring
Install Prometheus for monitoring AWS:
	•	Install and connect Blackbox exporter, Node exporter with Prometheus.
Installing Grafana:
	•	Install Grafana on an EC2 instance.
	•	Connect Prometheus with Grafana.

Conclusion: 
This CI/CD Pipeline Project harnesses the power of leading DevOps tools and practices to create a streamlined, efficient, and reliable software delivery process. By integrating GitHub, Jenkins, Docker, Kubernetes, SonarQube, Nexus, Prometheus, and Grafana, this project ensures that code is built, tested, and deployed seamlessly while maintaining high standards of code quality and application performance.

Through automated builds, continuous deployment, and robust monitoring, teams can achieve greater development agility and operational excellence. This setup not only reduces the time to market but also enhances the ability to respond to changes and issues swiftly. By following the steps outlined in this README, you can set up your own CI/CD pipeline and leverage the benefits of a modern DevOps ecosystem, driving your projects towards success with confidence and ease.


