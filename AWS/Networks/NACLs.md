# Network Access Control Lists (NACLs)

- Associated with a subnet
- There are inbound and outbound access control lists
- By default allows all inbound and outbound traffic
- They are stateless so any response to a request has to be explicitly allowed
- Each subnet can only have one NACL
- But a NACL may be associated with many subnets
- Each rule in the table defines:
  - Type (e.g. HTTP, HTTPS)
  - Protocol
  - Port range
  - Source or Destination (depending on whether it's inbound or outbound)
  - Allow/Deny
- You tend to have a deny rule for all traffic not matching one of the allow access rules
- `0.0.0.0` means any IP
