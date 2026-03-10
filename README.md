## terraform-eks-cluster

This project automates the deployment of a managed **Amazon EKS (Elastic Kubernetes Service)** cluster using **Terraform (HCL)**

## Architecture

- **Cloud Provider:** AWS
- **Infrastructure Tool:** Terraform (HCL)
- **Kubernetes Version:** 1.31
- **Network:** Custom VPC with Public/Private subnets, NAT Gateway and Route Tables.
- **Compute:** Managed Node Group used `t3.micro` instances.

## Prerequisites

Before running this, you need:

- [Terraform](https://www.terraform.io/downloads.html) installed.
- [AWS CLI](https://aws.amazon.com/cli/) configured with your credentials.
- [kubectl](https://kubernetes.io/docs/tasks/tools/) to interact with the cluster.

## How to Use

1. **Initialize Terraform:**
   ```bash
   terraform init
   terraform plan
   terraform apply -auto-approve
   ```
2. **Verify:**
   aws eks update-kubeconfig --region us-east-1 --name dex-infra-cluster
   kubectl get nodes

3. **Cleanup:**
   terraform destroy -auto-approve
