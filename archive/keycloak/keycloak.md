### Setup

Based on [this](https://github.com/bitnami/charts/tree/main/bitnami/keycloak/).

# Helm install

Install the chart:
```
helm upgrade --install keycloak oci://registry-1.docker.io/bitnamicharts/keycloak --create-namespace --namespace keycloak -f values.yaml
```