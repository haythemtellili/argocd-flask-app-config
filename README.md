# argocd-flask-app-config

# install ArgoCD in k8s
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
# access ArgoCD UI
```
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd
```
```
# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
```

# Other commands
```
kubectl get svc -n flask-app
```
```
kubectl port-forward svc/flask-service 3003:3000 -n flask-app
```