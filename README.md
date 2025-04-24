# argocd_doc
🚀 Application Deployment using Argo CD on AWS EKS
This project demonstrates deploying a Kubernetes application on Amazon EKS and managing it via Argo CD. The setup uses kubectl, AWS CLI, and Kubernetes YAML files (service.yaml and deployment.yaml) for resource creation.

✅ Project Setup Overview
Kubernetes Cluster: Provisioned on AWS EKS using the AWS CLI.

Argo CD: Installed and running inside the EKS cluster.

Application: Deployed using service.yaml and deployment.yaml files.

GitOps Workflow: Managed entirely via Argo CD's Web UI and GitHub repo sync.

📦 Steps Followed
Created an EKS cluster using AWS CLI.

Installed Argo CD inside the cluster using the official manifests.

Accessed Argo CD UI via port-forwarding:

kubectl port-forward svc/argocd-server -n argocd 8080:443
Logged in to Argo CD, created a new application pointing to the GitHub repo.

Synced the application, deploying the resources defined in:

deployment.yaml

service.yaml

Verified deployments using kubectl:
kubectl get pods
kubectl get svc
📊 Argo CD UI Highlights
App Health: ✅ Healthy

Sync Status: ✅ Synced to Git commit 90e26ae

Live Tree View: Visualizes all Kubernetes resources — Deployment, Service, ReplicaSet, Pods, etc.

Rollback/History: Easily manage deployment rollbacks.

📂 Repo Structure
.
├── deployment.yaml
├── service.yaml
└── README.md
