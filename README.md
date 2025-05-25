# AWS_Solutions_Architect-Manara
# Scalable Web Application on AWS with ALB and Auto Scaling

## Project Overview
This project demonstrates how to deploy a highly available and scalable web application on AWS using EC2 instances, Application Load Balancer (ALB), and Auto Scaling Groups (ASG). The architecture ensures fault tolerance, load distribution, and automatic scaling based on traffic demands.

## Architecture
The solution is deployed within a Virtual Private Cloud (VPC) that contains multiple Availability Zones (AZs) for high availability. Key components include:

- **Public Subnets (AZ-1 & AZ-2):** Hosts the Application Load Balancer and EC2 instances.
- **Application Load Balancer (ALB):** Distributes incoming traffic across multiple EC2 instances.
- **Auto Scaling Group (ASG):** Automatically scales EC2 instances based on load metrics.
- **Private Subnets (Multi-AZ):** Hosts the Amazon RDS database instances for high availability and failover.
- **IAM Roles:** Secure and role-based access for EC2 instances.
- **CloudWatch & SNS:** Monitoring performance metrics and sending alerts on thresholds.

![Architecture Diagram](https://github.com/MaiMHanafi/AWS_Solutions_Architect-Manara/blob/main/Blank%20diagram.png)

## Key AWS Services Used
- **Amazon EC2** - Compute capacity for hosting the web application.
- **Application Load Balancer (ALB)** - Traffic distribution and fault tolerance.
- **Auto Scaling Group (ASG)** - Automatic scaling of instances based on demand.
- **Amazon RDS** (Optional) - Multi-AZ database backend (MySQL/PostgreSQL).
- **IAM Roles** - Secure access management for EC2 instances.
- **CloudWatch & SNS** - Performance monitoring and notifications.

## Features
- Highly available multi-AZ architecture.
- Load balancing with ALB.
- Auto-scaling EC2 instances for cost and performance optimization.
- Secure role-based access with IAM.
- Database failover support with Multi-AZ RDS.
- Automated monitoring and alerting using CloudWatch and SNS.

## Getting Started

### Prerequisites
- AWS Account with sufficient permissions.
- AWS CLI configured.
- Basic knowledge of AWS services.

### Deployment Steps

1. **Set up the VPC and Subnets**  
   Create a VPC with two public and two private subnets across two AZs.

2. **Launch RDS Instances**  
   Deploy Multi-AZ Amazon RDS instances in private subnets.

3. **Create Security Groups**  
   Configure security groups for ALB, EC2 instances, and RDS.

4. **Deploy EC2 Instances with IAM Roles**  
   Launch EC2 instances in public subnets with an attached IAM role.

5. **Configure Auto Scaling Group and ALB**  
   Set up an Auto Scaling Group with desired scaling policies and associate it with the ALB.

6. **Set up CloudWatch Monitoring and SNS Alerts**  
   Configure CloudWatch alarms to monitor CPU and other metrics; integrate with SNS for notifications.

7. **Test the Application**  
   Access the ALB DNS name and verify load balancing and scaling behavior.



---

## 🔧 Project Components in more detailed explanation

### 🧱 Virtual Private Cloud (VPC)
A logically isolated network that hosts all the AWS resources (subnets, EC2s, databases, etc.).

---

### 🌐 Public Subnets (AZ-1 & AZ-2)

#### 🔁 Application Load Balancer (ALB)
- Entry point to the application.
- Distributes incoming HTTP/HTTPS traffic to healthy EC2 instances across AZs.

#### 💻 EC2 Instances (Web Servers)
- Hosted in an **Auto Scaling Group**.
- Automatically scales in/out based on demand (e.g., CPU > 70%).
- Web application is deployed here (e.g., Node.js, Flask, etc.).

#### 🔐 IAM Role for EC2
- Allows secure access to other AWS services (e.g., S3, CloudWatch) without hardcoding credentials.

---

### 🔐 Private Subnets (Multi-AZ)

#### 💾 Amazon RDS (MySQL/PostgreSQL)
- Managed relational database service.
- Multi-AZ deployment for **high availability and failover**.
- Only accessible from the EC2 web servers.

---

### 📊 Monitoring and Alerts

#### 🧠 Amazon CloudWatch
- Monitors system metrics (CPU, memory, disk, etc.).

#### 📩 Amazon SNS (Simple Notification Service)
- Sends email/SMS notifications when alarms are triggered (e.g., high CPU).

---

## GitHub Repository
All project code, scripts, and deployment instructions are available at:  
[https://github.com/MaiMHanafi/AWS_Solutions_Architect-Manara.git]


## Author
Mai Mohamed Hanafi - maihanafi34@gmail.com
