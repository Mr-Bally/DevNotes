# IPsec

- IPsec: Internet Protocol Security
- Suite of protocols and algorithms to secure IP data at the Network Layer
- Provides
  - Confidentiality via encryption
  - Integrity (hashing)
  - Authentication (signature and certificates)

## Components

- Authentication Header (AH)
  - Allows the receiver to verify the sender is who they say they are
  - Check the packet hasn't been modified
  - Ensure there is no replay attack
  - Does NOT ensure the privacy of the data
- Encapsulating Security Protocol (ESP)
  - Encrypts the data in the message

### Sub components

- Confidentiality: DES, 3DES, AES
- Integrity: MD5, SHA
- Authentication: PSK, RSA
- Key Exchange: Diffie Hellman (DH1-DH7)

## IPSec Connection Creation

- Uses Internet Key Exchange Protocol (IKE)
  - Phase 1: Endpoints negotiate to authenticate one another and create session keys and establish the tunnel
  - Phase 2: Use the tunnel to establish the SA (which encrypts the data) and IPsectunnel via key exchange

### Modes

- Transport Mode:
  - Used between end stations or an end station and a gateway (if the gateway is being treated like a host)
  - Does not encrypt the IP header, just the payload
  - Often used for client to site VPN scenarios
- Tunnel Mode:
  - Encrypts the body and IP header
  - A new IP header is then created
  - Often used for site to site comms

## AWS Usage

- Each AWS VPN connection has 2 tunnels
- Each tunnel uses a unique Virtual Private Gateway's public IP address
- This is done for redundancy
- VPG connects a VPC to one or more customer gateways
