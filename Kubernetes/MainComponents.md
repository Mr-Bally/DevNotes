# Main Components

## Nodes

- Server where resources are deployed
- Can be a physical machine or a VM

## Pod

- Abstraction over a container
- Smallest unit of a K8s cluster
- Can run one or many Containers in a Pod
- Each Pod has its own IP address
- If a Pod dies and is recreated, a new IP address is used

## Service

- Can be attached to one or more Pods
- Has a permanent IP address
- Lifecycle of a Pod and a Service is not connected
- Allows Pods to communicate with each other
- Service load balances between multiple load balanced Pods

## Ingress

- Allows the forwarding of external traffic to the Services

## Config Map

- External config of your app (database URLs etc)
- Based on key-value pairs

## Secret

- Like ConfigMap but for storing sensitive data
- Base64 encoded for usernames, passwords etc
- Can also use 3rd party services to encrypt and store secrets

## Volumes

- Allow data to persist outside the life of a Pod
- Storage can be on the local machine or external
- This is external to the K8s cluster

## Deployment

- Blueprint for Pods (e.g. how many replicas)
- Abstracts away from managing indiviual Pods
- Should only be used for stateless apps
- Deploys a replicaset
- Should not have to directly manage the Pods below the Deployment
- Deployments are only concerned with Pods not the Services used to interact with them

## Replicaset

- Manages the replicas of a given Pod

## StatefulSet

- Meant specifically for deploying and managing stateful apps
- Use case would be something like a database
- IE where data needs to be persisted
