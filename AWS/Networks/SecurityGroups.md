# AWS Security Groups

- Used for filtering inbound and outbound traffic
- Act on the instance level rather than the subnet level
- They are stateful (IE you don't need to configure them for return traffic)
- Act as a virtual firewall between subnets
  - E.g. only one subnet can communicate with the subnet which hosts the database
- SG rules are evaluated after the NACL rules
- Each SG contains:
  - Type (e.g. MYSQL, AURORA)
  - Protocol
  - Port Range
  - Source
- By default all SG rules are considered Allow
- If there is not a rule then trafic is denied
