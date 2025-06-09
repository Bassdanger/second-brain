A pod is the smallest element on a Kubernetes cluster
Pod of Whales
A pod is not a container
A pod is a collection of containers + other resources

- Single container
- Multi container
- Initcontainer
- Networking
- Storage

k exec -it nginx-docs -- /bin/sh
k get pods -o wide