### Setup

# Helm install

Add helm repo:
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
```

Update helm repo cache:
```
helm repo update
```

Install cert-manager:
```
helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx \
  --namespace ingress-nginx --create-namespace
```