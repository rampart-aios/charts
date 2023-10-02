# Helm charts for non-OCI helm 3 clients
## How to add/remove helm chart from an OCI registry

### 1. Checkout repop and create a feature branch
```
git clone git@github.com:rampart-aios/charts.git
git checkout -b my_feature
```
### 2. Login GitHub OCI registry
```
helm registry login ghcr.io
```
### 3a. Pull the helm charts from OCI registry
- Get Helm URL from GitHub Packages: For example: "docker pull ghcr.io/rampart-aios/coordinator/coordinator-chart:0.1.0-33302cec"
- Pull Helm Chart with pull script
```
./scripts/pull.sh "docker pull ghcr.io/rampart-aios/coordinator/coordinator-chart:0.1.0-33302cec"
```
### 3b. Delete unused snapshot from OCI registry
```
rm rampart-ui-0.2.0-xxxx.tgz
```

### 4. Update index
```
helm repo index .
```

### 4. Commit your change
```
git add .
git commit -m "Added new chart!"
git push --set-upstream origin my_feature
```

### 5. Submit your MR for review
