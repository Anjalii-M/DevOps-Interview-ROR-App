# Continuous Deployment

## CI Pipeline

1. Checkout Source Code
2. Build Rails Docker Image
3. Build Nginx Docker Image
4. Push Rails Image to Amazon ECR
5. Push Nginx Image to Amazon ECR

---

## CD Pipeline

The CD pipeline updates only the ECS nested CloudFormation stack.

Infrastructure stacks such as VPC, RDS, IAM, ALB and S3 are not modified.

Deployment command:

```bash
aws cloudformation deploy \
--stack-name Mallow-CF-ECSStack-XXXX \
--template-file infrastructure/ecs/cluster.yaml
```

Each deployment updates

- ECS Task Definition
- ECS Service

A rolling deployment is automatically performed by Amazon ECS.

Docker images are versioned using the Jenkins Build Number.

Example:

rails_app:45

nginx-app:45
