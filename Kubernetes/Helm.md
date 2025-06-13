Package manager for kubernetes
helm repo add - adds repo to system
helm install homarr homarr-labs/homarr --name homarr --create-namespace
values.yaml - contains all the default vlaues and all the things you can pass
helm ls -A
helm uninstall -n homarr homarr
helm upgrade -n homarr homarr homarr-labs/homarr --values=values.yaml