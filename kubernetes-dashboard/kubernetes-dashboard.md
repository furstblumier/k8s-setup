### Setup

# Helm install

Add helm repo:
```
helm repo add kubernetes-dashboard https://kubernetes.github.io/dashboard/
```

Update helm repo cache:
```
helm repo update
```

Install kubernetes-dashboard:
```
helm upgrade --install kubernetes-dashboard kubernetes-dashboard/kubernetes-dashboard --create-namespace --namespace kubernetes-dashboard -f values.yaml
```