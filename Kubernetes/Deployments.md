k delete deployments.apps test
k create deploy -h | vim 
k create deployment mealie --image=nginx --dry-run=client -o yaml > deployment.yaml
