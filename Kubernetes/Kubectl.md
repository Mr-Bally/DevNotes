# Kubectl

- Kubectl is the K8s command line
- API server on the Master Nodes responds to these commands
- Can install a tool like MiniKube to run K8s on a single Node (your machine)

## MiniKube Commands

- `minikube start --driver docker`
- `minkube status`
- `minkube addons enble ingress`
  - Starts the K8s NGINX implementation of the Ingress Controller Component

## Kubectl Commands

- `kubectl get nodes`
  - Check Nodes status
- `kubectl version`
- `kubectl get pod`
  - Check Pods status
- `kubectl get services`
  - Check Services status
- `kubectl create deployment <deploymentName> --image=<imageName>`
  - e.g. `kubectl create deployment nginx --image=nginx`
- `kubectl get replicaset`
  - Replicasets manages the replicas of a Pod
- `kubectl edit deployment <deploymentName>`
  - Modify a deployment e.g. request an additional Pod gets created
- `kubectl logs <podName>`
- `kubectl describe <component>`
  - Describes changelog for a component e.g. Pod
- `kubectl exec -it <podName> -- <shell>`
  - e.g. `kubectl exec -it mongo-pod -- bin/bash`
  - Starts an interactive terminal within a Pod
- `kubectl delete deployment <deploymentName>`
  - Delete a deployment and all underlying resources
- `kubectl apply -f <fileName>`
  - Create a deployment from a config file
  - This can be for any Component (e.g. Service, Role etc)
- `kubectl delete -f <fileName>`
  - Remove a Component which is defined by the file
- `kubectl get namespaces`
- `kubectl create namespace <namespace>`
