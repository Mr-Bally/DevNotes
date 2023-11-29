# Architecture

## Node

- Also known as a worker machine
- Each Node typically has multiple Pods
- 3 Processes are installed on each Node
  - Container Runtime: Usually Docker but can be another technology.
    - This starts the Pod with a Container inside it
  - Kube Proxy: Forwards the request to the relevant Pod via the Service

## Master Node

4 Processes run on every Master Node:

- API Server: This is how you interact with the Cluster (like a Gateway)
  - Use it for updating and querying in the cluster
  - Also handles authentication requests to the Cluster
  - Validates the requests and forwards on the request to other processors if successful
- Scheduler: Decides which Node to deploy the Pod to (e.g. does this Node have enough memory for this new Pod)
  - Makes requests to the Node's Kublet process
- Controller Manager: Detects states changes (such as Pods dying)
  - Tries to keep the state of the Cluster consistent
  - Makes requests to the Scheduler to recover dead Pods
- etcd: The Cluster brain and is a key-value store
  - Cluster changes get stored here
  - Scheduler uses it for information about the Nodes
  - Controller Manager uses it to check the Cluster and Pod health
  - Application data is not stored here

## Cluster Setup

- Typically a Cluster is made up with several Master servers
- Master Servers typically consume fewer resources than worker Nodes
- Can keep adding in physical machines or VMs to a Cluster as demand increases
- Or remove them as demand wanes

## Namespaces

- Way of organising resources into logical groups
- Creating a virtual cluster inside the 'main' K8s cluster
- Some components are not tied to a namespace but are global
- For example Volumes
- Can use the `-n <namespace>` to interact with a given namespace

## Best Practice

- Don't put everything in the same namespace
- Potential for overwriting if multiple teams are deploying to the same namespace
- Do not modify the default namespaces (e.g. kube-system)
- Allows you to perform green/blue deployments
- Can restrict users to only modifying resources to specific namespaces
- Can limit the resources a namespace can consume to prevent a monopoly on the servers resources

## Admins and Users

- Admins setup and maintain the cluster
  - Including managing storage resources and creating Persistant Volume Storage
- Users deploys into the Cluster
  - And use resources like Volumes created by the admins
  - By creating Persistant Volume Claims
