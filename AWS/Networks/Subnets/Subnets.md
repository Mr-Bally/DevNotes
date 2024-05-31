# Subnets

- Appear within a VPC
- Allow you to segment the VPC into multiple networks
- Each subnet gets a CIDR block range which is a subnet of the containing VPC CIDR block range
  - This is done by using different subnet masks
- Each subnet is deployed to an AWS AZ
  - This allows for redundancy
- First 4 IPs of a subnet CIDR are reserved for:
  - Network
  - AWS routing
  - AWS DNS
  - AWS future use
- And the very last IP is used as a broadcast address

## Public Subnet

- Are accessible to the external internet
- Have an internal IP address whcih is within their subnet CIDR range
- A public IP address for access through the internet

## Private Subnet

- Not directly accessible via the internet

## Config

- Both public and private subnets are created in the same way
- But if a subnet has a route to an internet gateway then it is considered public
  - Typically this is set as `0.0.0.0/0` in the route table
- Note, an internet gateway attaches to a VPC not the subnet

### Route tables

- Each subnet has a single route table
- On VPC creation an implicit router is created called the Main Route Table
- Subnets will be associated with this by default unless a custome route table is created
- The same route table can be used for multiple subnets
- By default, a local route is created to allow subnets in the same VPC to communicate with one another
- `0.0.0.0/0` means any request not matching an IP in the route table should go to this target

### Routing Priorities

- If there are overlapping destination network ranges AWS will default to using the most precise one
  - Known as longest prefix match (IE which has the longest network mask)
- Unless:
  - Route propagation is enabled for a virtual gateway and those routes overlap the local route. The local route with have precedence even if the propagated route has the longest prefix
  - If any propagated routes have the same destination as static routes. Check docs for the order.

### Flow Logs

- Capture traffic going in and out of a subnets network interface
- Can be configured to filter what traffic to log
