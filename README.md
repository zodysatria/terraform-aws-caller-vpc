## VPC Caller

Usage example:

```
provider "aws" {
  version = "~> 3.0"
  profile = "example"
  region  = "us-east-1" #N.Virginia
}

module "vpc" {
  source = "terraform-aws-modules/vpc/aws"

  name = "poc-vpc-terraform-example"
  cidr = "10.0.0.0/21"

  azs             = ["us-east-1a", "us-east-1b"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24"]
  public_subnets  = ["10.0.3.0/24", "10.0.4.0/24"]

  enable_nat_gateway = true
  enable_vpn_gateway = false

  tags = {
    Managedby   = "Terraform"
    Environment = "poc"
  }
}


```
