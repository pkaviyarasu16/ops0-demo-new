# EC2 Instance with t2.micro

This Terraform configuration creates an EC2 instance with t2.micro instance type.

## Resources Created

- EC2 instance (t2.micro) with Amazon Linux 2
- Security group with HTTP (80) and SSH (22) access
- Basic web server setup via user data

## Prerequisites

1. AWS CLI configured with appropriate credentials
2. An existing EC2 key pair in your AWS account
3. Terraform installed (>= 1.0)

## Usage

1. Copy the example variables file:
   ```bash
   cp terraform.tfvars.example terraform.tfvars
   ```

2. Update `terraform.tfvars` with your values:
   - Set your key pair name
   - Update SSH CIDR blocks for security
   - Customize other variables as needed

3. Initialize Terraform:
   ```bash
   terraform init
   ```

4. Plan the deployment:
   ```bash
   terraform plan
   ```

5. Apply the configuration:
   ```bash
   terraform apply
   ```

## Accessing the Instance

After deployment, you can:

1. SSH to the instance using the output command
2. Access the web server at `http://<public_ip>`

## Security Notes

- Update `ssh_cidr_blocks` to restrict SSH access to your IP only
- Consider using a bastion host for production environments
- The security group allows HTTP access from anywhere (0.0.0.0/0)

## Cleanup

To destroy the resources:

```bash
terraform destroy
```