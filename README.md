# Helm Repository
A repository of *packaged* Helm charts for the [Bioconductor](https://bioconductor.org) project.

To update charts manually, place a copy of the packaged chart(s) into
the `charts` folder and (re)build `index.yaml` by running the following command
in this repo's root:


Example

```
## created myawesomechart-7.7.7.tgz
git clone https://github.com/Bioconductor/helm-charts
cp myawesomechart-7.7.7.tgz helm-charts/charts/myawesomechart-7.7.7.tgz
cd helm-charts
helm repo index . --url https://github.com/Bioconductor/helm-charts/raw/main
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

RStudio-Helm: https://github.com/bioconductor/rstudio-helm
