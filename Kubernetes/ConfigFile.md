# Kubernetes Configuration File

Files are written in YAML and contain a defintion for a K8s Component such as a Service or Deployment.

## File Section

### Metadata

- Contains data like the labels and name of the components

### Spec

- Configuration for the Component
- each Component has it's own specific specification

### Template

- Inside the specification is the template
- This contains the metadata and a spec (essentially config within config)
- This is a blueprint for a Pod

### Status

- Automatically generated and checked by K8s
- Constantly checks the status to see if something is different between the file and what is deployed
- Backbone of K8s and self healing
- Information is added to the file by K8s from etcd

## Labels and Selectors

- Metadata section contains Labels
  - They are a key-value pair e.g. `app: nginx`
- Spec section contains Selectors whcih match on a label
- This allows the Deploment to know which Pod belongs to is
- This works across different YAML files (see examples in sub dir)
