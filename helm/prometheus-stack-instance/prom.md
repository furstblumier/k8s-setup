## Setup

# Helm install

Add helm repo:
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
```

Update helm repo cache:
```
helm repo update
```

Install prom-stack:
```
helm upgrade --install kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 62.6.0 --namespace prometheus-stack --create-namespace --values values.yaml
```