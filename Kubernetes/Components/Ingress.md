# Ingress

## External Service vs Ingress

- Can use an External Service and hit via an IP address
- However, ideally you want to use a domain name for the final product
- So instead you would use an Ingress which in turn redirects the request to an Internal Service

## Ingress Component

Contains:

- `rules` for routing traffic
- `path` for defining the HTTP path
- The backend interval service to map the requests to
- `host` is hte valid domain name which maps to the Node's IP address and is the entrypoint
- `tls` for configuring the TLS certificate with a reference to the Secrets Store where it's stored

## Ingress Controller

- You can't just use an Ingress Component
- You will also need an Ingress Controller
- This is another set of Pods which evaluates and processes ingress rules
- It acts as the entrypoint to the Cluster
- There are many third-party implementations you can use (including a K8s NGINX controller)
- Typically you would configure a proxy infront of the K8s cluster for load balancing and security

### Example Ingress YAML

This creates an ingress to the default K8s dashboard namespace and Pods

You could define multiple paths which map to different internal services. This means that different paths forward to different Services and Pods. You could also have multiple hosts which map to different URLs to different services

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: dashboard-ingress
  namespace: kubernetes-dashboard
  annotations:
    kubernetes.io/ingress.class: "nginx"
spec:
  rules:
  - host: dashboard.com
    http:
      paths:
      - path: /
        pathType: Exact
        backend:
          service:
            name: kubernetes-dashboard
            port:
              number: 80
```
