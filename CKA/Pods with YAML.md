apiVersion, kind, metadata, and spec required
pod-definition.yml

apiVersion: v1
kind: Pod
metadata:
	name: myapp-prod
	labels:
		app: myapp

spec: 
	containers:
		- name: nginx-container
		   image: nginx

kubectl create -f pod-definition.yml
kubectl apply -f pod-definition.yml
kubectl get pods
kubectl describe pod myapp-prod

kubectl run redis --image=redis123 --dry-run=client -o yaml - outputs the yaml that will be made

kubectl run redis --image=redis123 --dry-run=client -o yaml > redis.yaml - sends it to an actual redis file