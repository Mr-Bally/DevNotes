# Roles

- Define the permissions a user or a group can perform
- Can be specific to a namespace or a particular resource
- These are bound to the user/group via a Role Binding

## Cluster Roles

- You can define Cluster Roles for Cluster level opeations such as viewing the namespace etc
- You can then bind to these defined roles using the Cluster Role Binding

## Service Account

- Some applications will also need permissions (including Cluster-level)
- Such as Jenkins for deployments, Istio or Prometheus
- Each Pod gets a Service Account which they can use to speak to K8s
- Each Service Account uses tokens to authenticate with the API server
- Every Service Account should have Least Privaledge
