# Network Policy

- By default all Pods in a Cluster can speak to all othe rPods
- However this is not secure
- If one Pod becomes compromised then all other Pods can be interacted with
- Network Policy allows you to define Network rules including:
  - Which Pods can speak to one another
  - What traffic Pods can accept
    - e.g. Front End Pod can only speak to the Back End Pod but not the Database Pod
- So if one Pod becomes compromised it limits the possible damage
- This Network Policy is implemented by a Network Plugin
  - Without a Network controller the rules will not be enforced

## Service Mesh

- Network Policy os defined on the Network level
- You can use a Service Mesh such as Istio to configure traffic on the Service level
- Service Mesh also allows you to enable mTLS between Pods to encrypt the traffic
- Prevent attackers from reading the plain text
