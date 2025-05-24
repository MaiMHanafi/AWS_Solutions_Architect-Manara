# AWS_Solutions_Architect-Manara
# Scalable Web Application with ALB and Auto Scaling

## Project Overview
This project demonstrates deploying a scalable and highly available web application on AWS using EC2, Application Load Balancer (ALB), and Auto Scaling Group (ASG). It showcases how to optimize cost and performance by automatically adjusting the number of instances based on demand.

## Architecture
- EC2 instances in multiple availability zones running the web app.
- ALB distributing incoming traffic across EC2 instances.
- ASG automatically scales EC2 instances based on load.
- Amazon RDS Multi-AZ for backend database.
- CloudWatch monitors the application and triggers scaling.
- SNS alerts notify stakeholders on scaling events or alarms.

## AWS Services Used
- EC2, ALB, ASG
- Amazon RDS
- IAM Roles
- CloudWatch & SNS

## Deployment Instructions
1. Clone the repo.
2. Launch EC2 instances with the provided user-data script or AMI.
3. Configure ALB and attach target groups.
4. Setup Auto Scaling policies (scale out at 70% CPU, scale in at 30% CPU).
5. Deploy RDS instance.
6. Configure CloudWatch alarms and SNS notifications.

## Testing the Application
- Access the ALB DNS URL to see the web app.
- Use load testing tools (e.g., Apache JMeter) to simulate traffic and observe scaling.

## Cost Optimization
- Use spot instances in ASG.
- Set min and max instance counts appropriately.
- Use RDS instance types matching workload.

## Monitoring & Alerts
- CloudWatch CPU Utilization alarms.
- SNS email notifications on scaling events.

## Author
Mai Mohamed Hanafi - maihanafi34@gmail.com
