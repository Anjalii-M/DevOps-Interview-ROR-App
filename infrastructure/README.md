# DevOps Interview - Ruby on Rails Application Deployment

## Project Overview

This project demonstrates deploying a Ruby on Rails application on AWS using Infrastructure as Code (CloudFormation) and a CI/CD pipeline implemented with Jenkins.

The infrastructure is modularized using nested CloudFormation stacks and deployed on AWS ECS Fargate.

---

# Architecture

The infrastructure consists of:

- VPC
- Public & Private Subnets
- Internet Gateway
- NAT Gateway
- Security Groups
- Application Load Balancer
- ECS Fargate Cluster
- PostgreSQL RDS
- Amazon S3
- IAM Roles
- CloudWatch Logs

---

# Infrastructure Templates

| Template | Purpose |
|----------|----------|
| vpc.yaml | Creates VPC, Subnets, Route Tables |
| security-groups.yaml | Creates ALB, ECS and RDS Security Groups |
| s3.yaml | Creates Application S3 Bucket |
| iam.yaml | ECS Task Roles and S3 Permissions |
| rds.yaml | PostgreSQL Database |
| alb.yaml | Application Load Balancer |
| cluster.yaml | ECS Cluster, Task Definition and Service |
| master.yaml | Deploys complete infrastructure using nested stacks |

---

# CI/CD Workflow

GitHub
↓

Jenkins

↓

Build Docker Images

↓

Push Images to Amazon ECR

↓

Update ECS Nested CloudFormation Stack

↓

Rolling Deployment on ECS Fargate

---

# Application Stack

- Ruby on Rails
- Puma
- Nginx
- PostgreSQL
- Amazon S3
- ECS Fargate

---

# AWS Services Used

- CloudFormation
- ECS Fargate
- ECR
- IAM
- ALB
- RDS PostgreSQL
- S3
- CloudWatch
- VPC

---

# Repository Structure

```
docker/
infrastructure/
app/
config/
Jenkinsfile
docker-compose.yml
README.md
```

---

# Deployment Documentation

Refer:

- Deployment.md
- Jenkins-CD.md
- Architecture.md
- Architecture-Design.png