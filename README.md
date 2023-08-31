# Helm charts for non-OCI helm 3 clients
## How to add helm chart from a OCI registry

### 1. Checkout repop and create a feature branch
```
git clone git@github.com:rampart-aios/charts.git
git checkout -b my_feature
```
### 2. Login GitHub OCI registry
```
helm registry login ghcr.io
```
### 3. Pull the helm charts from OCI registry
```
helm pull oci://ghcr.io/rampart-aios/rampart-ui-chart/rampart-ui --version 0.2.0-94a6662f
```

### 4. Commit your change and submit MR
```
git add .
git commit -m "Added new chart!"
git push
```
