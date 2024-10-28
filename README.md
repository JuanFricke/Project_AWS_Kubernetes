# ☁️ Final Project for Compass UOL Scholarship Program | AWS and DevSecOps - AWS Infrastructure for Fast Engineering eCommerce

## 📋 Project Members
- Bruno Silveira: https://github.com/brunohsilv
- Edilson Maria: https://github.com/EdilsonMaria
- Felipe Santos: https://github.com/Felipe53650
- Laura Capssa: https://github.com/laura-capssa
- Juan Paulo: https://github.com/juanfricke

---

## 🔎 **CASE:**
Fast Engineering S/A is a rapidly growing e-commerce company. Since the beginning of the year, access and purchases have been increasing by 20% each month. The current on-premise architecture, composed of dedicated servers for the application, web server, and database, can no longer support the high demand for access and purchases. Therefore, the chosen solution was to migrate the environment to AWS cloud, ensuring scalability, security, and high availability for the e-commerce platform.

### **Current Architecture**
Currently, the on-premise environment consists of:
- **1 Database Server (MySQL)**
- **1 Application Server (React)**
- **1 Web Server**, which also stores static files like photos and links.

<img src="/imgs/arq_atual.png">
Current architecture of Fast Engineering

---

## 🆕 **New Cloud Architecture (AWS)**

The migration solution involves implementing an AWS architecture designed to ensure high availability, scalability, and security.

### **New Architecture Description:**

1. **User accesses Fast Engineering's e-commerce site** via **AWS Route 53**, which handles DNS traffic routing.

2. **AWS WAF** is used for security, protecting against malicious attacks and access.

3. Static content (such as photos and links) will be distributed globally using **Amazon CloudFront** to reduce latency and improve user experience.

4. Traffic arrives at a **Load Balancer (Application Load Balancer - ALB)**, which distributes requests to containers and microservices.

5. **Containerized application managed by EKS (Elastic Kubernetes Service)** using **AWS Fargate**. 
   - **Pods running the front-end (React)**.
   - **Pods running a Web Server (Nginx)**.
   - **Pods managing DB connection**.
   - **Pods managing S3 and EFS connection**.
   - **Pods collecting logs**.

6. The database will be migrated to **Amazon RDS (MySQL)** with Multi-AZ configuration, ensuring high availability and automatic backups.

7. **AWS CodePipeline** and **AWS CodeDeploy** will be used for continuous integration and deployment (CI/CD) of the application, ensuring automation and efficiency in updates.

8. **AWS CloudWatch** will be configured to monitor service health and send alerts for any anomalies.

9. Permission management will be handled with **AWS IAM** to ensure security and access control.

<img src="/imgs/arq_aws.png">
Fast Engineering's AWS Architecture

<img src="/imgs/arq_kubernetes.png">
Internal Kubernetes Architecture

---

## 🧰 **Services and Resources Used in the Architecture**

1. **AWS Route 53**: DNS management service that allows routing users to different AWS resources based on defined rules, such as geographical proximity or service health.

2. **AWS WAF (Web Application Firewall)**: Web application firewall that protects against common internet threats, like SQL injection, cross-site scripting (XSS), and DDoS attacks.

3. **Amazon CloudFront**: Content distribution (CDN) service that accelerates the delivery of static or dynamic content globally, reducing latency for end users.

4. **Application Load Balancer (ALB)**: Load balancer that distributes traffic across different instances or containers, ensuring traffic balancing and redirecting failures to healthy instances.

5. **Amazon EKS (Elastic Kubernetes Service)**: Managed Kubernetes service that orchestrates containers, enabling scalability, automation, and quick deployment of microservice applications.

6. **AWS Fargate**: Serverless container execution service that eliminates the need to provision and manage servers. Containers run on demand with Fargate.

7. **Amazon S3 (Simple Storage Service)**: Scalable and secure storage service that allows static file storage, like images and videos, with high durability and accessibility.

8. **Amazon EFS (Elastic File System)**: Shared file system allowing multiple instances or containers to access the same file system simultaneously, ideal for data-sharing scenarios.

9. **Amazon RDS (MySQL)**: Managed relational database allowing high availability configuration (Multi-AZ) and automatic backups for redundancy and quick recovery in case of failure.

10. **AWS CodePipeline and AWS CodeDeploy**: Continuous integration (CI) and continuous delivery (CD) services that automate the processes of building, testing, and deploying the application.

11. **AWS CloudWatch**: Monitoring service that collects and tracks metrics, logs, and events from AWS, sending alerts and enabling health and performance tracking for the infrastructure.

12. **AWS IAM (Identity and Access Management)**: Identity management service that allows defining granular permissions to access and manage AWS resources securely.

---

## 💰 **Budget**

### Cost Estimate for the New Architecture

- [AWS Calculator Link](https://calculator.aws/#/estimate?id=eddd7d07382facf5f41f637a4d8dfc3b31f629a5)

<img src="/imgs/princing_calculator.png">
Cost Estimate for the New Architecture

- Monthly cost: 2,016.31 USD

- Total 12-month cost: 24,195.72 USD

---

## 📬 **Timeline**
<!-- Divide the migration timeline by stages -->
To be attached.

---

## 📑 **References**
- [AWS Route 53](https://aws.amazon.com/route53/)
- [AWS WAF](https://aws.amazon.com/waf/)
- [Amazon CloudFront](https://aws.amazon.com/cloudfront/)
- [Elastic Load Balancer](https://aws.amazon.com/elasticloadbalancing/)
- [Amazon EKS](https://aws.amazon.com/eks/)
- [AWS Fargate](https://aws.amazon.com/fargate/)
- [Amazon S3](https://aws.amazon.com/s3/)
- [Amazon RDS](https://aws.amazon.com/rds/)
- [AWS CodePipeline](https://aws.amazon.com/codepipeline/)
- [AWS CloudWatch](https://aws.amazon.com/cloudwatch/)
- [AWS IAM](https://aws.amazon.com/iam/)
