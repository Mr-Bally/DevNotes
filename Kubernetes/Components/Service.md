# Kubernetes Service

- Each Pod has an IP address
- But they are ephemeral and new Pods get different IP addresses
- Service offer a stable IP address and a way for us to communicate with a Pod
- Promotes loose coupling between Pods
- Services also offer loadbalancing

## Ports

- Services have to define a port for receiving traffic to itself
- And a target port fo rthe Pod it is forwarding the requests onto
  - For example, forwarding requests to a MongoDB pod listening on port 8080
  - Example YAML below
- The target port should match whatever was defined in the Deployments file -> Spec -> Template -> Spec -> Containers -> Ports -> Container Port

```yaml
ports:
  - protocol: TCP
    port: 80
    targetPort: 8080
```

## Making a Service External

- To make a Service usable from outside the Cluster you must change the `type` to `LoadBalancer`
- This assigns it an external IP address to accept requests
- You also need to assign a `nodePort` which is the port the requests will be sent to externally

Example

```yaml
apiVersion: v1
kind: Service
metadata:
  name: mongo-express-service
spec:
  selector:
    app: mongo-express
  type: LoadBalancer
  ports:
    - protocol: TCP
      port: 8081
      targetPort: 8081
      nodePort: 30000
```

## Services

### ClusterIP Service

- Default Service type
- Acts as a proxy for one/many Pods
- Selectors define which Pods the Service should forward to by matching to the Pod labels
- Also defines the target port for where to forward the requests to

### Multi-Port Service

- Some Pods may have more than one port exposed
- For example, a sidecar container for exporting logs
- This allows you to define multiple ports
- However, you then have to name each of the ports

### Example

- Ingress receives traffic from the outside
- Forwards the traffic into the Cluster to a Cluster IP Service
- Cluster IP Service then loadbalancing the traffic to the Pods

### Headless Service

- For when you want to communicate with a specific Pod
- Rather than a random load balanced Pod
- Such as when you are using a Stateful application like a database
- You might need to communicate to the Master Pod to write to the database
- If you set the ClusterIP to None in the Service YAML file
  - When the DNS looksup a Service it will return a Pod IP address
  - Rather than the Service Cluster IP (none is assigned to the Service)

## Service Types

### Cluster IP

- Default

### NodePort

- Creates a Service which is available on a static Port on each Node in the Cluster
- So a Cluster IP can be accessed only from within the Cluster or via an Egress
- However, with a Node Port external traffic can hit this static port and data is routed directly to the Node Service
- This Service spans all the Worker Nodes
- Node Ports are not secure as you are opening ports to talk directly to the work Nodes
- It is also not particularly efficient

### Load Balancer

- The Service creates the following:
  - Cloud Load Balancer (Google, AWS etc)
  - ClusterIP Service
  - NodePort: Port open on the Cluster but only for the Cloud LB
- Cluster becomes accessible thorugh this Load Balancer
