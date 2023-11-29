# K8s Commands

## minikube

* `minikube start --driver docker` : Start local minikube cluster hosting it in Docker
* `minikube status` : Check local minikube cluster
* `minikube service <service-name> --url` : Create a tunnel for minikube to expose the service, service name from meta data

## kubectl

* `kubectl cluster-info` : View cluster information
* `kubectl get all` : Get all information about Kubernetes pods, deployments, services and more
* `kubectl get <component>` : Get information about K8s component e.g. pod, sv, node, all
* `kubectl get pod -o wide` : Get extended information about a K8s components (works with all standard get options)
* `kubectl apply -f <path-to-resource>` : Create resource on a K8s cluster, e.g. config, deployment
* `kubectl delete all --all --namespace default` : Remove all resources in namespace (default is the ...default namespace), note this does not affect configmaps and secrets
