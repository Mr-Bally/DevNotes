# Storage Class

- Volumes are good, however for large applications deployed in K8s provisioning can be tedious
- For example, creating hundreds of Volumes manually for dozens of deployed applications
- Storage Class provisions Persistent Volumes dynamically when a Persistent Volume Claim claims it

## Configuration

- The YAML file defines details such as the Provisioner
  - IE the storage type such as AWS EBS
- Parameters configure the underlying storage details (which depends on the Provisioner)
- The PVC configuration would now point at a Storage Class rather than a specific PV
