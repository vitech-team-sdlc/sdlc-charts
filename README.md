# sdlc-charts

### Repo
https://vitech-team.github.io/sdlc-charts/

### Install
Chart Releaser: https://github.com/helm/chart-releaser

### Release
 
```shell
CHART_NAME="tektonpipelines"
PACKAGE_PATH="./.release"
PACKAGE_ALL_PATH=".cr-release-packages"
cr package charts/${CHART_NAME} --package-path="$PACKAGE_PATH"
cr upload "charts/${CHART_NAME}" --config="./config.yaml"  --package-path="$PACKAGE_PATH"
cp -R "$PACKAGE_PATH/." $PACKAGE_ALL_PATH
git add $PACKAGE_ALL_PATH
cr index --config="./config.yaml" -i index.yaml --pages-branch=main
rm -rf "$PACKAGE_PATH"
```