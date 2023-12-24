#### helm charts

```sh
helm lint charts/prometheus
helm package charts/prometheus
helm repo index --url https://jeremiebidault.github.com/helm-charts/ --merge index.yaml .
```

#### install with value file

```sh
cat <<EOF > prometheus-values.yaml
EOF

helm upgrade --install prometheus . --values prometheus-values.yaml --namespace monitoring --create-namespace
```

#### install without value file

```sh
helm upgrade --install prometheus . --namespace monitoring --create-namespace
```

#### uninstall

```sh
helm uninstall prometheus -n monitoring
```
