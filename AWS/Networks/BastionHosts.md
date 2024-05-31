# Bastion Hosts

- Allows a user to make a connection request to resources hosted in a private subnet
  - But they cannot default to use a NAT/Internet Gateway
  - For example, EC instances
- Bastion Hosts allow connections coming from specific sources (e.g. SSH) through the internet gateway
- The resources in the private subnet will need a security group to allow incoming traffic from the Bastion Host
- You should not store the private SSH key on the Bastion Host
  - Generally it is better to use an SSH forwarding client
