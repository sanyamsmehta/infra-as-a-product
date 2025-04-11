# infra-as-a-product

This project demonstrates a fully automated infrastructure setup on AWS using Pulumi (Python runtime). The goal was to create a scalable, production-grade deployment pipeline that provisions all necessary cloud resources dynamically—ideal for spinning up ephemeral environments, internal dev tooling, or lightweight production workloads.

The infrastructure setup emphasizes modularity, cloud-native best practices, and minimal manual intervention. 

**This Pulumi IaC script provisions:**
An ECS Cluster with Fargate for serverless container orchestration
An nginx containerized service behind an Application Load Balancer
A properly scoped IAM role for ECS task execution
An EC2 Security Group to expose HTTP & ICMP traffic
A highly available setup across VPC subnets (pulled dynamically)
Environment-based config management using Pulumi.yaml and pulumi.dev.yaml

**Use Cases**
Rapid infrastructure bootstrapping for internal tools
Demo/proof-of-concept environments for product features
Lightweight container hosting without EC2 overhead
IaC onboarding sandbox for engineering teams
Dev/test environments that can be spun up and destroyed on demand

**Tech Stack**
Pulumi (Python runtime)
AWS ECS + Fargate
Load Balancer (ALB)
IAM, VPC, EC2 Security Groups
JSON-based container definitions

**Extensibility Ideas**
This project can be easily extended to include:
CI/CD integration via GitHub Actions or CircleCI
HTTPS via ACM + Route53 + ALB Listener Rules
Auto-scaling based on CloudWatch metrics
Multi-container task definitions (e.g., sidecar containers)
Parameterized environments (staging, prod, etc.)
