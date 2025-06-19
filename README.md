# 🚀 Argo CD Deployment on AWS EKS

![GitHub Repo Size](https://img.shields.io/github/repo-size/HARSHITHA-G-M/argocd_doc)
![GitHub Last Commit](https://img.shields.io/github/last-commit/HARSHITHA-G-M/argocd_doc)
![GitHub Stars](https://img.shields.io/github/stars/HARSHITHA-G-M/argocd_doc?style=social)
![GitHub Watchers](https://img.shields.io/github/watchers/HARSHITHA-G-M/argocd_doc?style=social)

---

## 📘 Overview

This project demonstrates a **GitOps-based deployment pipeline** using **Argo CD** to manage applications on **AWS EKS (Elastic Kubernetes Service)**.

It uses Kubernetes manifests (YAML) for deployment, and Argo CD monitors the Git repository to automatically sync changes into the EKS cluster.

---

## 🧰 Tools & Technologies

| Tool            | Purpose                                      |
|------------------|----------------------------------------------|
| 🐳 Docker         | Containerization                             |
| ☸️ Kubernetes     | Container orchestration via EKS              |
| 🔁 Argo CD        | GitOps-based Continuous Delivery              |
| ☁️ AWS EKS        | Managed Kubernetes cluster                   |
| 📄 YAML Manifests | Declarative infrastructure & app specs       |

---

## 📁 Repository Structure

argocd_doc/
├── prod/ # Environment directory (production)
│ └── app.yaml # ArgoCD application spec
├── deploy.yml # Kubernetes Deployment manifest
└── README.md # Project documentation


---

## 🔧 Setup Instructions

### Prerequisites:
- AWS CLI configured
- `kubectl` installed and connected to EKS
- Argo CD installed on EKS
- GitHub repository created (this one!)

### 🛠️ Steps:

1. **Connect to your EKS cluster**
```bash
aws eks --region <region> update-kubeconfig --name <cluster_name>

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl apply -f prod/app.yaml
kubectl port-forward svc/argocd-server -n argocd 8080:443

👩‍💻 Author
Harshitha G M

⭐ Support
If you found this useful:

Give it a ⭐

📜 License
This project is licensed under the MIT License.

Share it with DevOps learners


