# sdlc-charts

### Repo
https://vitech-team.github.io/sdlc-charts/

### Install
Chart Releaser: https://github.com/helm/chart-releaser

### Release
 
```shell
CHART_NAME="largetests"
cr package charts/${CHART_NAME}
cr upload "charts/${CHART_NAME}" --config="./config.yaml"
cr index --config="./config.yaml" -i index.yaml --pr  --pages-branch=main
```