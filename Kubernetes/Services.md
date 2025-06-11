A service offers a consistent address to access a set of pods
Why?
- Pods are ephemeral (throw away). should not expect them to have a long lifespan
- Pods are constantly changing and being moved across nodes.
- How will the system keep track of the constantly changing IP addresses?

k expose deployment frontend --port 8080
k get service 
k get svc

Services
- ClusterIP - default. creates cluster-wide IP for the service
- NodePort - exposes a port on each node allowing direct access to the service through any node's IP address
- LoadBalancer - Used for cloud providers. Willc reate an azure LoadBalancer to route traffic into the cluster.

k port-forward services/mealie 9000