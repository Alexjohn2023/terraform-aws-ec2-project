# Terraform AWS EC2 Project

## Project Overview

This project demonstrates how to provision an AWS EC2 instance using Terraform.

The goal of this project is to teach beginners how to provision Infrastructure as Code (IaC) on AWS using Terraform and Amazon Web Services, it demostrates the real DevOps workflow. 

WHAT I BuILT
I provisioned an AWS EC2 instance using Terraform.
The instance was created with:

resource "aws_instance" "my_server" {
  ami           = "ami-0c02fb55956c7d316"
  instance_type = "t2.micro"

  tags = {
    Name = "terraform-server"
  }
}

---

## Tools Used

- Terraform
- AWS
- AWS CLI
- VS Code
- Git Bash

---

Step-by-Step Workflow

First, I created a Terraform project folder:

terraform_05

Inside the folder, I created two main files:

provider.tf
main.tf

In provider.tf, I configured the AWS provider:

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

Then I initialized Terraform:

terraform init

This downloaded the AWS provider and created:

.terraform/
.terraform.lock.hcl

Next, I validated my configuration:

terraform validate

Terraform confirmed:

Success! The configuration is valid.

Then I previewed what Terraform would create:

terraform plan

After reviewing the plan, I applied the configuration:

terraform apply

Terraform created my EC2 instance successfully:

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.

I then checked the AWS EC2 console and confirmed that my instance named:

terraform-server

was running successfully.

Finally, I destroyed the infrastructure to avoid unnecessary AWS charges


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

