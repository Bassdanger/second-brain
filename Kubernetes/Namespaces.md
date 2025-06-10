kubectl get pods -n mealie
k run mischa-mealie --image=nginx -n mealie
k config set-context --current --namespace=mealie set as default
