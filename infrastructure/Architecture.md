# Architecture

The application is deployed using AWS ECS Fargate.

## Components

### Networking

- Custom VPC
- 2 Public Subnets
- 2 Private Subnets
- Internet Gateway
- NAT Gateway

### Compute

- ECS Cluster
- ECS Service
- Task Definition
- Rails Container
- Nginx Container

### Load Balancing

- Application Load Balancer
- Target Group

### Database

- Amazon RDS PostgreSQL

### Storage

- Amazon S3

Authentication is performed using the ECS Task IAM Role.

No Access Keys or Secret Keys are stored inside the application.

### Logging

CloudWatch Logs

### IAM

- ECS Execution Role
- ECS Task Role

Task Role provides S3 permissions.
