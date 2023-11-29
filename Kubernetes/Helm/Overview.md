# Helm Overview

## Use Cases

### Package Manager

- Can distribute and share Helm charts from repositories to many users
- Packages all the different Kubernetes Components into a Helm Chart
- Means common deployments (e.g. databases like Mongo) can be done quickly without lots of configuring

### Template Engine

- Typically different YAML files have common values
- Helm allows you to swap out dynamic or common values with placeholders
- These template files are rendered prior to the Helm chart being deployed

### Release Management

- Helm uses Tiller on the K8s Cluster to keep a record of Helm releases
- Means you can easily rollback

## Structure

- `Chart.yaml` : Meta information about the Chart
- `values.yaml` : Values to be rendered into the template files
- `charts/` : Contains the Chart dependencies
- `templates/` : Contains the template files

You can have several different value files and pass in the different files and performing the Helm install command
