# AWS Networking Infrastructure with Terraform

This project provisions a custom AWS networking environment using Terraform. The goal was to build a foundational cloud architecture with public and private subnets, internet routing, NAT-based outbound access, security groups, and EC2 instances.

## Project Overview

This infrastructure was built to demonstrate core AWS networking concepts and Infrastructure as Code practices, including:

- Custom VPC creation
- Public and private subnet design
- Internet Gateway configuration
- NAT Gateway for private outbound internet access
- Public and private route tables
- Route table associations
- Security group configuration
- Public and private EC2 deployment
- Terraform-based provisioning and teardown

## Architecture Components

### Networking
- 1 custom VPC
- 2 public subnets
- 2 private subnets
- 1 Internet Gateway
- 1 Elastic IP
- 1 NAT Gateway
- 1 public route table
- 1 private route table
- subnet-to-route-table associations

### Security
- Public security group allowing SSH only from a restricted source IP
- Private security group allowing SSH only from the public security group

### Compute
- 1 public EC2 instance
- 1 private EC2 instance

## Terraform Files

### `main.tf`
Defines the AWS infrastructure resources.

### `variables.tf`
Defines reusable input variables such as:
- `ami_id`
- `key_name`

### `terraform.tfvars.example`
Shows the expected variable values needed to deploy the project.

### `outputs.tf`
Can be used to display useful resource outputs after deployment.

## Terraform Workflow Used

### Initialize Terraform
```bash
terraform init