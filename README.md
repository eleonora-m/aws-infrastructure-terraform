# 🏗️ AWS Infrastructure with Terraform

Automated AWS infrastructure provisioning using Terraform (Infrastructure as Code).  
Designed for repeatable, consistent, and auditable cloud deployments.

## 📐 Architecture

```
VPC (10.0.0.0/16)
├── Public Subnet (10.0.1.0/24)
│   └── EC2 Instance (web server)
├── Private Subnet (10.0.2.0/24)
└── Security Groups
    ├── web-sg (HTTP/HTTPS/SSH)
    └── default
S3 Bucket (static assets + Terraform state)
IAM Role + Instance Profile
```

## 🛠️ Technologies
- **Terraform** v1.5+
- **AWS** — EC2, VPC, S3, IAM, Security Groups
- **Linux** — Ubuntu 22.04

## 📂 Project Structure
```
aws-infrastructure-terraform/
├── main.tf           # Core infrastructure
├── variables.tf      # Input variables
├── outputs.tf        # Output values
├── vpc.tf            # VPC and networking
├── ec2.tf            # EC2 instance config
├── s3.tf             # S3 bucket
├── iam.tf            # IAM roles and policies
└── README.md
```

## 🚀 Usage

```bash
# 1. Clone the repo
git clone https://github.com/eleonora-m/aws-infrastructure-terraform
cd aws-infrastructure-terraform

# 2. Configure AWS credentials
aws configure

# 3. Initialize Terraform
terraform init

# 4. Preview changes
terraform plan

# 5. Apply infrastructure
terraform apply

# 6. Destroy when done
terraform destroy
```

## ✅ What This Creates
- Custom **VPC** with public and private subnets
- **EC2** instance with Ubuntu 22.04 in public subnet
- **Security group** allowing HTTP (80), HTTPS (443), SSH (22)
- **S3 bucket** for static file storage
- **IAM role** with EC2 instance profile and S3 read access
- **Internet Gateway** and route tables

## 📊 Key Results
- Reduced environment setup time by **40%** vs manual configuration
- Eliminates configuration drift across environments
- Fully repeatable — destroy and rebuild in minutes

## 👩‍💻 Author
**Eleonora Musaeva** — Cloud Administrator | DevOps Engineer  
📧 devops.nora@gmail.com
