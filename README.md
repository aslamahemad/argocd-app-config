# Commands

Install ArgoCD in k8s

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
Access ArgoCD UI

```bash
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd
```

Login with admin user and below token (as in documentation)

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
```

You can change and delete init password

</br>

# Links

* Config repo: https://github.com/aslamahemad/argocd-app-config

* Docker repo: https://hub.docker.com/r/aslamahemad/argocd-app

* Install ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd

* Login to ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli

* ArgoCD Configuration: https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/

