# Helm Repository
A repository of *packaged* Helm charts for the [Bioconductor](https://bioconductor.org) project.

## Using charts from this repository
In order to use charts from this repository, you must first add the repository using:

```bash
helm repo add bioc https://github.com/Bioconductor/helm-charts/raw/devel
# helm repo update
```

You can then install any chart from the repository using the chart's name:
```bash
helm install myrelease bioc/bioconductor
```

See each chart's source repository for more details and configuration options.


## Updating chart manually

To update charts manually, place a copy of the packaged chart(s) into
the `charts` folder and (re)build `index.yaml` by running the following command
in this repo's root:


Example

```
## created myawesomechart-7.7.7.tgz
git clone https://github.com/Bioconductor/helm-charts
cp myawesomechart-7.7.7.tgz helm-charts/charts/myawesomechart-7.7.7.tgz
cd helm-charts
helm repo index . --url https://github.com/Bioconductor/helm-charts/raw/devel
# helm repo index . --url https://github.com/$MY_FORK_NAME/helm-charts/raw/$MY_BRANCH_NAME
git add .
git commit -m "Added my awesome chart v7.7.7 manually"
git push
```

Note:
- When creating a fork or branch, the index needs to be rebuilt



# Auto-Packaging

The following charts get automatically versioned, packaged, and pushed into
this repository (on all branches) on each merged Pull Request in the chart's
source repository:

Bioconductor-Helm: https://github.com/bioconductor/bioconductor-helm
