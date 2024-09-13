### Setup

# Helm install

Add helm repo:
```
helm repo add jetstack https://charts.jetstack.io
```

Update helm repo cache:
```
helm repo update
```

Install cert-manager:
```
helm upgrade --install \
  cert-manager jetstack/cert-manager \
  --namespace cert-manager \
  --create-namespace \
  --version v1.12.0 \
  --set installCRDs=true
```

# Issuer

CF setup:
Follow the instructions [here](https://cert-manager.io/docs/configuration/acme/dns01/cloudflare/#api-tokens) to setup API Tokens.

Create the secret (don't forget to insert your API Token):
```
kubectl apply -f cloudflare-api-token-secret.yaml
```

Create your issuer:
```
kubectl apply -f cf-issuer-staging.yaml
```