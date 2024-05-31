# Elastic IP Addresses (EIPs)

- You will likely have some public and some private IP addresses
- Sometimes you will want a persistant IP address
  - IE one which does not get removed when a service or similar is removed
- EIPs provide this as it is associated to an AWS account rather than an instance
- So it persists even if you terminate the instance it is associated with (e.g. an EC2)
