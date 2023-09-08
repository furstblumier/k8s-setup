### Setup

Based on [this](https://github.com/oauth2-proxy/manifests/tree/main/helm/oauth2-proxy).

# Helm install

Add the repo:
```
helm repo add oauth2-proxy https://oauth2-proxy.github.io/manifests
```

Update helm repo cache:
```
helm repo update
```

Create a new github oauth app like described [here](https://kubernetes.github.io/ingress-nginx/examples/auth/oauth-external-auth/#example-oauth2-proxy-kubernetes-dashboard).
Write clientID, clientSecret and cookieSecret in `values.yaml`. cookieSecret is generated via `openssl rand -base64 32 | head -c 32 | base64`.

Install the chart:
```
helm upgrade --install oauth-proxy oauth2-proxy/oauth2-proxy --create-namespace --namespace oauth-proxy -f values.yaml
```