# EKS Cluster Setup Commands

## 1️⃣ Create EKS Cluster (Control Plane Only)

This command creates an EKS cluster with only the control plane (no worker nodes).

```bash
eksctl create cluster \
  --name=my-cluster \
  --region=eu-west-1 \
  --version=1.33 \
  --without-nodegroup
```

---

## 2️⃣ Create Managed Node Group

This command creates a managed node group and adds worker nodes to the cluster.

```bash
eksctl create nodegroup \
  --cluster=my-cluster \
  --region=eu-west-1 \
  --managed \
  --nodes-min=3 \
  --nodes-max=4 \
  --node-type=c7i-flex.large \
  --node-volume-size=20 \
  --ssh-access \
  --ssh-public-key=eks-nodegroup-key
```

- Minimum nodes: 2  
- Maximum nodes: 4  
- Instance type: t3.small  
- Disk size: 20 GB  
- SSH access enabled  

---

## 3️⃣ Associate IAM OIDC Provider

This command associates the IAM OIDC provider with the EKS cluster.  
It allows the cluster to create and manage AWS resources securely using IAM roles for service accounts (IRSA).

```bash
eksctl utils associate-iam-oidc-provider \
  --region=eu-west-1 \
  --cluster=my-cluster \
  --approve
```

---

## 4️⃣ Delete EKS Cluster

This command deletes the EKS cluster and all associated resources.

```bash
eksctl delete cluster \
  --name=my-cluster \
  --region=eu-west-1
```

---

## ✅ Summary

- Create control plane only cluster  
- Add managed worker node group  
- Associate IAM OIDC provider  
- Delete cluster when no longer needed  

---

**Author:** Your DevOps Setup  
**Tool Used:** `eksctl`


Kubectl config view
kubectl config current-context
aws eks update-kubeconfig --region <eu-west-1> --name <my-eks-cluster>

