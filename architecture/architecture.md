# AWS Project Architecture

## Architecture Flow

```text
User
  |
  v
AWS VPC
  |
  +--------------------+
  |                    |
  v                    v
EC2 Web Server         S3
  |                    |
  |                IAM Role
  |
  +----> CloudWatch
  |
  +----> Route 53 Private DNS
             |
             v
      web.devops.local



      Components
VPC
Custom VPC containing the required networking components.

EC2
Amazon Linux EC2 instance running Apache HTTP Server.

IAM
IAM Role attached to EC2 for secure S3 access.

S3
Private S3 bucket used for object upload and download testing.

CloudWatch
Used for EC2 CPU utilization monitoring.

Route 53
Private Hosted Zone used for internal DNS resolution.
Validation
DNS resolution:
nslookup web.devops.local
Application test:
curl http://web.devops.local
The Apache web server successfully returned the project web page.
