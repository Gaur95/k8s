# matrics server installation
```
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
```

# NGINX ingress controller installation 
```
git clone https://github.com/nginx/kubernetes-ingress.git --branch release-2.1
```
```
cd kubernetes-ingress
```
```
kubectl apply -f deployments/common/ns-and-sa.yaml
kubectl apply -f deployments/rbac/rbac.yaml
kubectl apply -f deployments/common/nginx-config.yaml
kubectl apply -f deployments/common/ingress-class.yaml
kubectl apply -f deployments/deployment/nginx-ingress.yaml
kubectl create -f deployments/service/nodeport.yaml
```
