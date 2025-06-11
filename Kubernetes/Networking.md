k port-forward pods/mealie-955d79855-rsxsl 9000
Pods
- Networking on pod level
- each pod gets its own ip address
- by default, pods can connect to all pods on all nodes
- containers in pods can communicate with each other through localhost
CNI Plugin - Container Networking Interface
- Provides network connectivity to containers
- Configures network interfaces in containers
- Assigns IP addresses and sets up routes
Implemented by CNI plugins
- Cilium
- Calico
- Flannel