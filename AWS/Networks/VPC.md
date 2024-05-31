# Virtual Private Clouds

- VPCs are an isolated part of the Cloud
- Only the AWS account whih created the VPC can access it
- Each VPC has:
  - A name
  - An IP CIDR block range (e.g. `10.0.0.0/16`)
- CIDR ranges in a VPC have a min/max of /28 to /16 (11 to 65531 hosts)
- It is mandatory to specify an IPv4 range but it is optional to have an IPv6 range

## VPC Peering

- Peering can be used to connect two VPCs together in 1 to 1 relationship
- You cannot route to a VPC via an intermediary
- The peering VPCs must use different, non-overlapping IP ranges
- Connections can be made within the same or different regions
- Peering connections are established in the order:
  - Request to VPC acceptor
  - Acceptor sends an acception to the request
  - Routing tables then need to be updated to reflect the changes
    - IE assign the destination VPC IP rnage to the PCX target in the table
  - Security Groups then need to be updated to allow the correct resources to be communicated with

## Transit Gateway

- Allows you to connect 1 to many VPCs
- Acts as a central hub
- Each VPC or external data centre connects to the transit gateway which then handles the routing
- Allows you to centralise network monitoring and logic

## VPC Endpoints

- Allow you to privately access AWS services using the AWS internal network
- Rather than connecting via public DNS endpoints in the internet
- Means you don't have to create an internet gateway etc
- Interface Endpoints
  - ENIs placed within a subnet
  - Act as a target for any traffic sent to a supported service
  - Operates using PrivateLink (AWS internal network)
- Gateway Endpoint
  - A target used in a route table for a supported service
  - Can be added to multiple VPC route tables
