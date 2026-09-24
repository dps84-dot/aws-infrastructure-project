# AWS Infrastructure & Cloud Deployment

## 📌 Project Overview

This project demonstrates a hands-on AWS infrastructure deployment using core AWS services.

The infrastructure includes networking, compute, storage, IAM-based access, monitoring, and private DNS resolution.

## 🛠️ AWS Services Used

- Amazon VPC
- Amazon EC2
- Amazon S3
- AWS IAM
- Amazon CloudWatch
- Amazon Route 53
- Apache HTTP Server
- Amazon Linux

## 🏗️ Architecture

```text
                         AWS
                          |
                       VPC
                          |
             +------------+------------+
             |                         |
           EC2                         S3
             |                         |
        Apache Web Server         Project Object
             |
       Private Route 53
             |
      web.devops.local
             |
       CloudWatch
       CPU Monitoring




      step 1. VPC & Networking
Created a custom VPC in the AWS Mumbai region.
Configured:
VPC
Subnets
Internet Gateway
Route Table
Routes
Security Group
Security Group rules were configured for:
SSH (22)
HTTP (80)
HTTPS (443)

step 2. EC2 Web Server
Created an EC2 instance named:
DevOps-web-server
Installed and configured Apache HTTP Server.
The web application was tested successfully using:
curl http://web.devops.local
Expected output:
DevOps AWS Project - Dharmendra


Step3. IAM Role
Created an IAM role:
Ec2-s3-access-role
The IAM role was attached to the EC2 instance to provide secure access to Amazon S3 without storing AWS access keys on the server.

Step 4. Amazon S3
Created an S3 bucket:
dharmendra-devops-project-2026
Tested:
S3 bucket listing
File upload
File download
Example:
aws s3 cp devops-test.txt s3://dharmendra-devops-project-2026/
Download test:
aws s3 cp s3://dharmendra-devops-project-2026/devops-test.txt ./downloaded-test.txt

Step5. CloudWatch
Configured an Amazon CloudWatch CPU utilization alarm for the EC2 instance.
Monitoring metric:
CPUUtilization
Threshold configured:
Greater than 70%

Step 6. Route 53 Private DNS
Created a Route 53 Private Hosted Zone for internal DNS resolution.
Configured:
web.devops.local
        |
        v
10.0.5.163
DNS resolution was tested from the EC2 instance using:
nslookup web.devops.local
Application connectivity was tested using:
curl http://web.devops.local
🔐 Security
EC2 access was controlled using Security Groups.
S3 access was provided using an IAM Role.
S3 Block Public Access was maintained.
No AWS access keys were stored on the EC2 instance.
Route 53 was configured as a private hosted zone.
🎯 Skills Demonstrated
AWS VPC networking
EC2 deployment
Linux administration
Apache web server configuration
IAM role-based access
S3 operations
CloudWatch monitoring
Route 53 private DNS
AWS CLI
Basic cloud security
📚 Project Outcome
Successfully deployed and tested an AWS infrastructure environment integrating compute, networking, storage, IAM, monitoring and private DNS services.
This project was created as a hands-on learning and DevOps practice project.
