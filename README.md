# AWS CloudFormation Template Library

This repository contains reusable AWS CloudFormation templates for common DevOps and cloud infrastructure patterns.

## Structure

- `networking/`
  - VPC + public/private subnets, IGW, route tables
- `compute/`
  - EC2 instances in public subnets
- `database/`
  - RDS MySQL instances in private subnets
- `storage/`
  - S3 static website hosting
- `iam/`
  - IAM roles and instance profiles (e.g., EC2 SSM role)

## Usage

1. Deploy `networking/vpc-2az-public-private.yaml` to create the base VPC.
2. Use the exported outputs (VpcId, subnet IDs) as parameters for:
   - `compute/ec2-public.yaml`
   - `database/rds-mysql-private.yaml`
3. Deploy S3 static website using `storage/s3-static-website.yaml`.
4. Attach IAM roles from `iam/` to EC2 instances where needed.

All templates are written in YAML and designed to be modular and reusable.
