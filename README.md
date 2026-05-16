# Terraform AWS EC2 Project

## Project Overview

This project demonstrates how to provision an AWS EC2 instance using Terraform.

The goal of this project was to learn Infrastructure as Code (IaC) using Terraform and AWS.

---

## Tools Used

- Terraform
- AWS
- AWS CLI
- VS Code
- Git Bash

---

## Project Structure

```text
terraform_05/
│
├── main.tf
├── provider.tf
├── README.md
├── .gitignore

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "6.45.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "my_server" {
  ami           = "ami-0c02fb55956c7d316"
  instance_type = "t2.micro"

  tags = {
    Name = "terraform-server"
  }
}

Terraform Commands

Initialize Terraform
terraform init

Validate Configuration
terraform validate

Preview Infrastructure
terraform plan

Provision Infrastructure
terraform apply

Destroy Infrastructure
terraform destroy

Key Takeaway:
Terraform basics
Infrastructure as Code
AWS provider configuration
EC2 provisioning
Terraform state management
Infrastructure lifecycle management

Conclusion
This is how DevOps engineers automate infrastructure using Terraform.

