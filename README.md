# ArgoCD example - GitOps

By: Dinesh Tripathi

## Getting Started with ArgoCD
### What is ArgoCD?
ArgoCD is a CD tool and works with kubernetes based resources.

### Lab Prerequisites

*  Minikube or any other kubernetes cluster is up and running

## This is an example of how to do a GitOps with ArgoCD.
### Lab Steps
* Step 1 - Create namespace
  ```sh
  kubectl create namespace argocd
  ```
* Install ArgoCD
  ```sh
  kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
  ```
* Port forward to access the service
  ```sh
  kubectl port-forward svc/argocd-server -n argocd 8080:443
  ```
* Run the below command to get the password and user username as admin
  ```sh
  kubectl get pods -n argocd -l app.kubernetes.io/name=argocd-server -o name | cut -d'/' -f 2
  ```
![Alt text](xyz/argocd.jpg?raw=true "ArgoCD Dashboard")  
