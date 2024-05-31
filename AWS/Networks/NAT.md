# Network Address Translation Gateway

- Component sits in a public subnet
- Has an elastic IP assigned
- Private subnet then adds a route to the NAT gateway (using 0.0.0.0/0 destination)
- NAT GW then sends an outbound request to the Internet Gateway
- NAT GW does not accept any inbound network traffic from the internet
- Only traffic which is returning due to a previous outbound request
