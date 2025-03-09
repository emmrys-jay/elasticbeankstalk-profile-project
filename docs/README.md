# Project Overview

## AWS Deployment with Elastic Beanstalk, RDS, Elasticache, and ActiveMQ
## Objective:
 The goal of this project is to set up a scalable AWS-based application environment using AWS Elastic Beanstalk for application deployment, RDS for database management, Amazon Elasticache for caching, and Amazon ActiveMQ for message brokering. The setup ensures secure communication through proper security group configurations, HTTPS via a CDN, and domain management through Route 53.

## Project Scope & Tasks:
1. Login to AWS Account
  - Access the AWS Management Console to begin the setup process.
2. Create Key Pair for Beanstalk Instance Login
  - Generate an SSH key pair to securely access the EC2 instances managed by Elastic Beanstalk.
3. Create Security Groups for AWS Resources
  - Define security groups for Amazon Elasticache, RDS, and Amazon ActiveMQ to restrict and manage access.
  - Security groups should be designed with the principle of least privilege, allowing only necessary inbound and outbound traffic.
  - The Beanstalk security group should have access to the database (RDS) and cache (Elasticache) to ensure seamless communication.
  - The security groups should also be configured to allow internal traffic between application components while blocking external access to sensitive services.
4. Provision AWS Services:
  - Create RDS Instance: Set up a managed relational database service.
  - Create Amazon Elasticache: Deploy a caching solution to improve performance.
  - Create Amazon ActiveMQ: Set up a managed message broker for communication between application components.
5. Create Elastic Beanstalk Environment
  - Deploy an Elastic Beanstalk environment to host the application backend.
6. Update Security Groups:
  - Allow traffic from the Beanstalk security group to the backend servers.
  - Configure security groups to allow internal communication among services while restricting public access to internal resources.
7. Launch EC2 Instance and Initialize MySQL Database:
  - Deploy an EC2 instance to access and initialize the RDS database.
  - Ensure database tables and necessary configurations are properly set up before deployment.
8. Modify Beanstalk Health Check Path:
  - Change the default health check URL to /login to match the application endpoint.
9. Add HTTPS Listener to Elastic Load Balancer (ELB):
  - The Elastic Beanstalk environment automatically provisions an ELB.
  - Configure the ELB to listen on port 443 for secure HTTPS traffic.
10. Build and Deploy Backend Application Artifact:
  - Update application.properties with connection details for RDS, Elasticache, and ActiveMQ.
  - Build the application artifact and deploy it to Elastic Beanstalk.
11. Configure CDN with SSL Certificate for HTTPS:
  - Set up a Content Delivery Network (CDN) [Cloudfront] to optimize content delivery and reduce latency.
  - Obtain and attach an SSL certificate to ensure secure communication.
12. Update Route 53 DNS Entries:
  - Configure Amazon Route 53 to point the domain to the Elastic Load Balancer.
  - Ensure DNS propagation is correctly configured to avoid downtime.
13. Test the Deployment:
  - Verify the application is accessible via the assigned domain.
  - Ensure all services (RDS, Elasticache, ActiveMQ) integrate properly with the backend.

## Expected Outcome:
 A fully functional, scalable AWS-hosted application with a secure and optimized infrastructure, leveraging Elastic Beanstalk, RDS, Elasticache, ActiveMQ, and Route 53 for DNS management. The architecture ensures high availability, security, and performance while maintaining ease of management.

## Prerequisite
Install JDK17+ and Maven 3.9.9

_Note:_ When creating your RDS (MySQL), make sure the Initial database name is "accounts". There are settings in the code that have been configured to look for a database called accounts.

---
GOODLUCK GUYS!!!
