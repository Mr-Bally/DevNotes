# Volumes

## Persistent Volumes

- Cluster level resource (IE not namespaced)
- Defines in the YAML file details such as:
  - Storage capacity
  - Volume Mode (type) e.g. Filesystem
  - Access modes
- It is an abstract Component however and needs physical storage (e.g. hard disc)
- This is simply an abstract interface to whatever storage medium you use
- YAML file attributes depend on what storage type is being used

## Persistent Volume Claims

- Persistent Volumes are created by the K8s cluster admins
- However it is the users deploying into the cluster that will want to use this
- So a Persistent Volume Claim must be created for the application to use the Volume
- The PVC must be added to the Pod config file to the Pod has access to the Volume
- The PVC must be defined in the same namespace as the Pod using it
- This allows the Volume to be mounted into the Pod and then into the Container
- A Pod can use multiple Volume types at once

## Config and Secret Components

- These are Volume types
- But they are not created by PV or PVCs
- They are created and managed by K8s
- You mount them to a Pod in the same way you would mount a Volume
