# Stateful Set

- Used for applications which store state like a database
- Not for stateless apps like a REST controller
- Stateless applications are deployed using Deployments (abstraction ontop of Pods)
- Stateful applications are deployed using StatefulSets

## Deployment vs StatefulSet

- It's more difficult to replicate a stateful application than a stateless one
- Stateless apps can be added and removed in any order
- Stateful apps cannot be as easily managed
- Each stateful app as a Pod identity unlike a stateless Pod which has a random hash
- StatefulSet maintains this identity for each Pod by using fix ordered names
- And each stateful Pod has a fixed DNS name
- Allows each Pod to retain its ID and state even if it dies and gets created

## Data Replication

- You have one Master Pod which is allowed to write data
- And Worker/Slave Pods who can read but not write data
- They do not have access to the same physical storage, instead they each have a replica of the database
- These replicas must be kept in sync at all times
