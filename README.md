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
# NGINX ingress controller installation using helm
## install helm 
```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```
## Add the Helm Repository
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
```
## Install NGINX Ingress Controller
```
helm install nginx-ingress ingress-nginx/ingress-nginx   --namespace ingress-nginx --create-namespace
```

## Verify Installation
```
kubectl get pods -n ingress-nginx
```
