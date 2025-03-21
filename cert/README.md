# install cert-manager
https://github.com/cert-manager/cert-manager/releases/download/v1.16.2/cert-manager.yaml
# steps for certificate
```
kubectl apply -f clusterissuer.yaml
kubectl apply -f certificate.yaml
```
## to verifiy
```
PS D:\desktop\k8s> kubectl get clusterissuer
NAME        READY   AGE
akashcert   True    24m
PS D:\desktop\k8s> kubectl get certificate  
NAME         READY   SECRET       AGE
ak-cert      True    akash-cert   2s 
PS D:\desktop\k8s> kubectl get secret
NAME         TYPE                DATA   AGE 
akash-cert   kubernetes.io/tls   2      2s
```
## now create ingress
```
kubectl get apply -f ingresswitcert.yaml
```
# to test
open https://k8s.akdev.live
