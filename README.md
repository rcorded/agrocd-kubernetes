# ArgoCD

[ArgoCD GitHub](https://github.com/argoproj/argo-cd)

[Getting Started](https://argo-cd.readthedocs.io/en/stable/getting_started/)

[Multiple configuration objects](https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/#multiple-configuration-objects)


kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl get pods -n argocd
kubectl port-forward svc/argocd-server -n argocd 8080:443
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

localhost:8080  
  login: admin
  password: 


change file django-app-secret.env and execute:
  kubectl create secret generic django-app-secret --from-env-file=./django-app-secret.env 

kubectl apply -f argocd/projects/
kubectl apply -f argocd/applications/helm-app.yaml