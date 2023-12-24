#### add/update chart

```sh
helm lint charts/prometheus

helm package charts/prometheus

helm repo index --url https://jeremiebidault.github.com/helm-charts/ --merge index.yaml .

helm repo add jeremiebidault https://jeremiebidault.github.io/helm-charts

helm search repo jeremiebidault
```

#### install/uninstall

```sh
cat <<EOF > prometheus-values.yaml
global:
EOF

helm upgrade --install prometheus . --values prometheus-values.yaml --namespace monitoring --create-namespace

helm uninstall prometheus --namespace monitoring
```
