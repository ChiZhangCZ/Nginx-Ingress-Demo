# Nginx Ingress Controller - Installation on AWS EKS

Based on files and instructions from: https://kubernetes.github.io/ingress-nginx/deploy/#aws
Requires an operational AWS EKS cluster.

YAML files required for Nginx Ingress Controller Installation(Layer 4-TCP mode)


# Installation

Create Ingress Controller deployment with required resources:
```
kubectl create -f controller.yaml
```

Create layer 4 load balancer(kubernetes service):
```
kubectl create -f servicel4.yaml
```

Create configmap for load balancer:
```
kubectl create -f configmapl4.yaml
```

