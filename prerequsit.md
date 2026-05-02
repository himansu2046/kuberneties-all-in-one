# 🚀 EKS Setup Commands

This file contains all the required commands to install and configure tools for working with Amazon EKS.

---

## 📌 1. Install kubectl

```bash
# Download kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# Make executable
chmod +x kubectl

# Move to PATH
sudo mv kubectl /usr/local/bin/

# Verify
kubectl version --client
