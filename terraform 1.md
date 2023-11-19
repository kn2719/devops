# Creating aws EC2 instance using terraform

Terraform is an open-source infrastructure as code (IaC) tool created by HashiCorp. It allows you to define and provision infrastructure in a declarative configuration language, enabling you to manage and version your infrastructure in a predictable and scalable way. 

Here's a basic workflow for managing infrastructure with Terraform:

Write the Terraform configuration to define your infrastructure.
Run terraform init to initialize your working directory.
Run terraform plan to see the execution plan.
Run terraform apply to apply the changes and create/update the infrastructure.
If needed, use terraform destroy to destroy the infrastructure.

Terraform installation:
Create instance named as terraform in ec2 instance 
Connect
sudo  su –
yum update -y
yum install terraform
write terraform download in browser
open terraform by hashicorp
click open source self managed terraform ‘
click linux and amazon linux
write all 3 commands 

sudo yum install -y yum-utils shadow-utils

sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo

sudo yum -y install terraform

terraform -v

hence installed
## Prerequisites

- AWS account
- Terraform installed
- AWS CLI installed
- AWS CLI configured with your credentials


## Procedure using terraform EC2 module (ez way)

1. Create a directory for your project and change into it.
2. Create a file named `main.tf` and add the following code to it:

``` hcl
module "ec2-instance" {
  source  = "terraform-aws-modules/ec2-instance/aws"
  version = "5.0.0"
}
```

3. Run `terraform init` to initialize the directory.
![terraform init](./assets/Ex-7/Ex-7.1.png)
4. Run `terraform plan` to see what Terraform will do.
![terraform plan](./assets/Ex-7/Ex-7.2.png)
5. Run `terraform apply` to create the resources.
![terraform apply](./assets/Ex-7/Ex-7.3.png)
![terraform apply](./assets/Ex-7/Ex-7.4.png)
![AWS EC-2 running](./assets/Ex-7/Ex-7.5.png)
6. Run `terraform destroy` to destroy the resources.
![terraform destroy](./assets/Ex-7/Ex-7.6.png)
![terraform destroy](./assets/Ex-7/Ex-7.7.png)
![AWS EC-2 terminated](./assets/Ex-7/Ex-7.8.png)

## Procedure using terraform aws provider

1. Create a directory for your project and change into it.
2. Create a file named `main.tf` and add the following code to it:

``` hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "devops-ex-7" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}
```
3. Run `terraform init` to initialize the directory.
4. Run `terraform plan` to see what Terraform will do.
5. Run `terraform apply` to create the resources.
6. Run `terraform destroy` to destroy the resources.
