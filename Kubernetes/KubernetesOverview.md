# Kubernetes

- - - -

## Overview

* Kubernetes (also called K8s) is an open source system for automating deployment, scaling and management of containerized applications
* Kubernetes is often described as orchestrating these containers
* Kubernetes can manage:
  * Load balancing
  * Storage orchestration
  * Automated rollouts and rollbacks
  * Self healing
  * Secret and configuration management
  * Horizontal scaling
* Benefits of using Kubernetes include:
  * Environment consistency
  * Shipping software faster
  * Eliminate app conflicts
  * Zero-downtime deployments
  * Orchestrates containers
  * Self-healing

## History

* Container and cluster management system was needed
* Internally used by Google for 15 years before being donated to the Cloud Native Computing Foundation
* It is now an open source project and supported by all major cloud platforms
* Allows for declarative configuration, e.g. I want `n` number of instances of this particular container running at all times

## General concepts

* One or more master nodes manage the worker nodes
* Worker nodes can be VMs or physical servers
* Together the worker and master node create a cluster
* Worker nodes contain Pods
* Pods "package" containers
* __etcd store:__ Data store for everything the master node needs to track
* __Controller manager:__ Manages incoming requests using Scheduler
* Worker nodes each have:
  * Kubelet which is used for communicating to the master node
  * Container run time
  * Kube-Proxy

## kubectl

* kubectl is a command line tool for sending requests to master node
* Master node then uses the scheduler for enacting requests

### Commands

* `kubectl cluster-info` : View cluster information
* `kubectl get all` : Get all information about Kubernetes pods, deployments, services and more
* `kubectl run <podName> --image=nginx:apline` : Run the nginx:apline container in a Pod
* `kubectl port-forward <podName> 8080:80` : Pods and containers are accessible within the Kubernetes cluster only by default. This exposes a container port externally

## Pods

* A pod is a basic execution unit of a kubernetes application
* It is the smallest /simplest unit in the Kubernetes object model you can create and deploy
* A Pod is an environment for containers
* You can organise parts of applications into pods (e.g. server, caching, APIs, database each in their own Pod)
* Each has a Pod IP, memory, volumes etc, shared across containers
* Pods scale horizontally by adding Pod replicas
* Pods live and die but never come back to life
* Pods do NOT span multiple nodes
* Pod containers share the same network namespace (IP/ port)
* Pod containers have the same loopback network interface (localhost)
* Container processes need to bind to different ports within a pod
* Can run a pod via they kubectl command line or with a YAML file
* If you delete a Pod, a new one will be recreated because of the Kubernetes deployment
* You would need to delete the deployment which is managing the Pods first of all

### Pod Health

* Pod health is determined via probes
* This is performed periodically via a kubelet on a container
* Probe types
  * Liveness Probe : Determines if a Pod is running as expected and healthy
  * Readiness Probe: Determines whether a Pod is ready to handle requests
* Failed Pod containers are restarted by default
* Type of check performed via the probe will depend on what is being run in the container
  * e.g. if it's a web server try a HTTP GET
* Probes can return either:
  * Success
  * Failure
  * Unknown
* Can define the probes in YAML

## Deployments

### Core concepts

* Replica Set : Declarative way to manage Pods
  * Including self-healthing mechanism
  * Fault tolerance  
  * Ensure the required number of Pods are running
  * Allow horizontal scaling of Pods
  * Relies on Pod templates
  * No need to create Pods directly

* Deployments : Declarative way to manage pods utiliziing Replica Sets
  * Scales Pods by scaling ReplicaSets
  * Supports zero-downtime update by creating and destroying Replica Sets
  * Provides rollback functionality

* Deployment options :
  * Rolling update : Deploys new Pods alongside older ones, when new Pod is ready an old one is removed
  * Blue / Green deployment : Multiple environments running concurretly then switch traffic once the environment has been proven working
  * Canary deployment : Small amount of traffic goes to new deployment to check service works as expected
  * Rollback

### Creating services

* A service provides a single point of entry for accessing one or more pods
* Can't rely on IP addresses being consistent especially as Pods can die
* Pods can be horizontally scaled so each Pod gets its own IP address when it is scheduled (not ahead of time)
* Services abstract Pod IP addresses from consumers
* Services load balance between the Pods
* Relies on labels to associate a Service with a Pod
* Node's kube-proxy creates a virtual IP for Services
* Services are not ephemeral (short lived)
* Services create endpoints which sit inbetween the Service and the Pod

* Service types:
  * Service can be defined in different ways
  * ClusterIP (default) : Expose the service on a cluster-interal IP
  * Only pods within the cluster can talk to the Service
  * Allows Pods talk to other Pods through Services

* NodePort : Expose the service on each Node's IP at a static port
  * Allocates a port from a range
  * Each Node proxies the allocated port

* LoadBalancer : Provision an external IP to act as a load balancer for the Service
  * Exposes a Service externally
  * Useful when used with a cloud provider's load balancer
  * NodePort and ClusterIP Services are created
  * Each Node proxies the allocated port

* ExternalName : Maps a Service to a DNS name
  * Service acts as an alias for an external service
  * Allows a Service to act as the proxy for an external Service
  * External Service details are hidden from the cluster (easier to change)

## Storage

* Volume : Can be used to hold data and state for both Containers and Pods
  * Volumes persist the data unlike Containers which lose their data
  * Pods can attach to several Volumes
  * Containers rely on a MountPath to access Volumes
  * Kubernetes supports (but not limited to):
    * Volumes
    * Persistant Volumes
    * Persistant Volume claims
    * Storage Classes
  * Volume references a storage location
  * Each Volume must have a unique name
  * The Volume is attached to a Pod and may or may not persist for the lifetime of the Pod

* Volume types:
  * emptyDir : Empty directory useful for storing transient data (shares a Pod's lifetime) and it used for sharing data between Containers running in a Pod
  * Host Path : Pod mounts to mounts filesystem
  * Network File System (NFS) : Mounted into the Pod
  * configMap / secrets : Special type of resource which
  * Persistant Volume Claim : Provides Pods with a more persistant storage option that is abstracted away from the details
  * Cloud : Cluster wide storage

### Persistent Volume (PV)

* Is a cluster-wide storage unit provisioned by an administrator with a lifecycle independent from a Pod
* To use a PV you use a Persistent Volume Claim to request access to the PV
* The PV relies on a network attached storage (NAS)
* Normally provisioned by a cluster administrator
* Available to a Pod even if it gets rescheduled to a different node
* Relies on storage provider such as NFS, cloud storage or other
* Associated with a Pod via a Persistent Volume Claim
* Kubernetes binds the PVC to the PV
* Pods then use the PVC to talk to the PV

### Storage Classes

* Storage Classes are a type of storage template that can be used to dynamically provision storage
* Defines different "classes" of storage
* Support dynamic provisioning of Persistent Volumes

1) Create Storage class (YAML)
2) Create PVC that references the Storage Class
3) Kubernetes uses Storage Class provisioner to provision a persistent volume
4) Storage provisioned, PV created and bound to PVC
5) Pod volume references PVC

## Config

### ConfigMap

* Stores configuration information and provides it to containers
* Can store entire files (key is the filename and the value is the contents which can be XML, JSON etc)
  * Or key-value pairs
* Can provide the config values via the command line
* Config Manifest file in YAML
* Config maps can be accessed from a Pod using:
  * Environment variables (key-value pairs)
  * ConfigMap Volume (access as files)

### Secrets

* Small amount of sensative data e.g. token, password or key
* Kubernetes can store this sensative data
* Avoids storing the data in images, files or deployment manifests which could be compromised
* Can mount secrets into Pods as files or environment variables
* Kubernetes only makes the secret available to nodes requesting it
* Secrets are stored ion tmpfs on a Node not on disc
  * Temporary File System) is a temporary file storage data is stored in volatile memory instead of a persistent storage device.

* Best Practice
  * Encrypt the data
  * Limit access to etcd (where secrets are stored to admins only)
  * Use SSL /TSL for etcd peer to peer communication
  * Manifest files are not encrypted
  * Control who can create Pods (as they can access the secret through the Pod)
