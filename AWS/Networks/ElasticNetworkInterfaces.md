# Elastic Network Interfaces (ENIs)

- Can be detached and reattached to a different EC2 instance
- By default EC2 instances are created with a Primary Network Interface (PNI) and labeled `ETH0`
- However, you might want an EC2 instance to have multiple network interfaces configured which is what ENIs provide
- For example, if you had two VPCs and wanted to route traffic from both to a single EC2

## Elastic Network Adapter (ENA)

- Custom interface to enhance network policy (e.g. 100GB/sec)
