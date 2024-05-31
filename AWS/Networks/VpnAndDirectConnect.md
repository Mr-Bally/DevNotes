# VPN and Direct Connect

## VPN

- Sometimes you may want to directly connect to a private subnet (not routing through a public subnet)
- To do so:
  - Add a virtual gateway to the private subnet, this is the endpoint for the communication
  - Add a customer gateway on the resource you want the private subnet to be communicated from
  - This allows a VPN tunnel to be established between the customer and virtual gateway
  - The tunnel can only be established from the customer side
  - The private subnet table would need updating to be able to communicate over the VPN
  - And the associated Security Group would need to allow incoming traffic from RDP

## Direct Connect

- Another method of connecting remote networks to a defined region which contains the desired VPC
- This uses private rather than public infrastructure
- Data is routed via a Direct Connect Location which is split between customer and AWS infrastructure
- DC Hops:
  - Data centre to public owned infrastructure in the DC location
  - DC location public infrastructure to DC location in AWS infrastructure
  - DC location AWS infrastructure to the specified region

## Virtual Private Gateway (VPG)

- Used to establish a VPN link between your VPC and corporate network
- Route table would need to include an entry to connect to the data centre

## Transit Gateway

- Acts as an endpoint for multiple VPCs to connect to an external customer gateway
