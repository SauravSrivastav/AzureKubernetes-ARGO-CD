Step 1: Create Namespace "argocd"
> kubectl create namespace argocd

Step 2: Deploy Argo-CD Manifest File:
> kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

Step 3: Change ClusterIP to Load Balancer of "argocd-server" to access ArgoCD UI:
> kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'

