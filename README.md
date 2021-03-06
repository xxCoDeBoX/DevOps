# DevOps
Infrastructure as a Code , Docker , Kubernetes with CI/CD Implementation for a python API.

# Summary
Its a python API which is deployed to eks with 3 replicaset.
Jenkins monitors GitHub for code changes and pipeline is triggred to build and push docker image of the application to ECR.
The Image is later deployed to EKS using service.json and controller.json for LoadBalancer and ReplicaController respectively.
Cloudformation is used to bring up Infrastructure which has 1 VPC , 2 Private Subnets , 2 Public Subnets 1 EKS Cluster 3 Worker Nodes.
All the worker nodes are deployed to Private subnet and controller is deployed to Public subnet.
Deployment strategy followed is Rolling updates.

# Application Configuration
Application runs on port 80 and the LoadBalancer is configured to port 80.

# Tools Used:
1. GitHub   - Code Repository
2. Jenkins - CI/CD
3. AWS EKS  - Container Orchestration
4. AWS ECR  - Image Repository

# Plugins Used:
1. Blue Ocean Plugin
2. AWS ECR Plugin
3. Docker Pipeline Plugin

In Groovy Script:
docker.withRegistry('https://xxxxx.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:creds')
The name creds is the credentails that you configured in Jenkins Global Configuration with AWS_ACCESS_KEY and AWS_SECRET_KEY
