- can only have one type of container in one pod
- pods can have multiple containers but all must be different
- helper containers - can be attached at the hip, created at same time, deleted at same time
	- need to make a map to track the 1 to 1 relationships of these containers
	- Pods handle this automatically
- kubectl
- kubectl run nginx --image nginx - deploys pod with container, gets nginx from docker hub
- kubectl get pods - see all pods
- 