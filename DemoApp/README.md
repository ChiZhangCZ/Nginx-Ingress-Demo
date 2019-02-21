# Example Web Application

Based on files and instructions from: http://rahmonov.me/posts/nginx-ingress-controller/

Tested on AWS EKS cluster with Nginx Ingress Controller installed.

YAML files required to deploy and connect to sample backend with Kubernetes and Nginx Ingress Controller. 

# Installation

Create sample backend deployment:
```
kubectl create -f nginxhello-deployment.yaml
```

Create service to link to deployment:
```
kubectl create -f nginxhello-service.yaml
```

Create Ingress to specify our path rules:
```
kubectl create -f nginxhello-ingress.yaml
```

# Testing

Find your Nginx Ingress Controller's External IP by the command:
```
kubectl get svc --namespace=ingress-nginx
```

Note: If you are running kubernetes on AWS, you will see a load balancer DNS instead of an IP, to get the IP you need run:
```
nslookup <Load Balancer DNS>

```
Configure the DNS names by appending your /etc/hosts file with:
```
<Nginx Ingress External IP>  nginxhello.com
```

Navigate to nginxhello.com and you should see a webpage with an Nginx heading and information about your deployment.
