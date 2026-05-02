# 🚀 EKS Setup Commands

This document contains all commands required to install and configure
tools for Amazon EKS.

------------------------------------------------------------------------

## 📌 1. Install kubectl

``` bash
# Download kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# Make executable
chmod +x kubectl

# Move to system path
sudo mv kubectl /usr/local/bin/

# Verify installation
kubectl version --client
```

------------------------------------------------------------------------

## 📌 2. Install AWS CLI

``` bash
# Update system packages
sudo apt update -y

# Install dependencies
sudo apt install -y unzip curl

# Download AWS CLI
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

# Extract files
unzip awscliv2.zip

# Install AWS CLI
sudo ./aws/install

# Verify installation
aws --version
```

------------------------------------------------------------------------

## 📌 3. Install eksctl

``` bash
# Download eksctl
curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_Linux_amd64.tar.gz"

# Extract archive
tar -xzf eksctl_Linux_amd64.tar.gz

# Move to system path
sudo mv eksctl /usr/local/bin/

# Verify installation
eksctl version
```

------------------------------------------------------------------------

## 📌 4. Configure AWS CLI

``` bash
aws configure
```

### Enter the following details:

-   AWS Access Key ID\
-   AWS Secret Access Key\
-   Default region (e.g., us-east-1)\
-   Default output format (json)

------------------------------------------------------------------------

## ✅ Verification Commands

``` bash
kubectl version --client
aws --version
eksctl version
```

------------------------------------------------------------------------

## ⚠️ Important Notes

-   Ensure IAM user has required permissions (EKS, EC2, IAM)
-   Never commit AWS credentials to GitHub
-   Prefer IAM roles over access keys for better security
