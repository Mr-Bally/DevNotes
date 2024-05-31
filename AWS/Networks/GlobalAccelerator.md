# AWS Global Accelerator

- Global service rather that being tied to a region
- Routes traffic through AWS managed network rather than the public internet
- Uses Edge locations for routing traffic
- Each Accelerator requires two IP addresses
- A Listener is then used to recieve and process incoming connections
- Each listener is associated with an Endpoint Group which is associated with a different region
  - You can then perscribe a traffic dial for the amount of traffic to send
