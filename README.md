# Booster Catalog
Set of known example applications (Boosters) conforming to the minimal set of requirements necessary to be served by launch.openshift.io.

- next: this is the branch from which we'll cut the next tag
- openshift-online-free; this is the branch read by launch.openshift.io and launch-stage.openshift.io.  Only the Boosters capable of running in the OSO Free environment are included here.

This repository is organized by `{mission}/{runtime}/{booster-catalog-entry}.yaml`:

For each booster (example application), create a YAML file in the respective `{mission}/{runtime}` directory with information containing:

Name   | Description 
------ | -----------
githubRepo| The GitHub repository location
gitRef | The git reference (tag/branch/SHA1)
boosterDescriptorPath|  (Optional) Path in the repository specified to `booster.yaml` (defaults to `.openshiftio/booster.yaml`)

The `booster.yaml` file beforementioned is expected to have the following structure:

Name   | Description | Required | Size
------ | ----------- | -----    | ----
name | The booster name  |  Yes  |  50
descriptionPath  |  (Optional) Link to file in repo containing adoc for the description (assumed default: `.openshiftio/description.adoc` ) |No  |  255
jenkinsfilePath | (Optional) Link to file in repo, relative to the repo root, for the Jenkins Pipeline Definition file (assumed default: `Jenkinsfile`) | No | 255
