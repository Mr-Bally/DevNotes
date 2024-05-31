# AWS Network Firewalls

- Managed service
- Allows fine grain control over network traffic
- Use cases include:
  - VPC to VPC traffic
  - Outbound traffic
  - Direct connect and VPN traffic
  - Internet traffic
- AWS Firewall endpoints are utilised so cost per endpoint needs to be considered

## Features

- Fully managed and HA with automated scaling
- Stateful firewall so session connections are saved and remembered for more granular filtering
- Web Filtering using Server Name Indication
- Intrusion Prevention System (IPS) protects againsts bots and brute force attacks
- Central management and visibility
- Alerts and flow logs
- Rule management

## Deployment Model

- Distributed
  - Firewall deployed into each individual VPC
  - Each firewall will have a policy (either individual or shared)
- Centralised
  - All network traffic is routed into a single VPC
  - Only a single firewall is required to monitor all the traffic

This deployment models can be mixed if needed.

## AWS Firewall Manager

- Can manage all firewall rules across all your AWS accounts and applications
