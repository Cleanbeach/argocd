# argocd

charts for argocd

## Att göra

- kommentera bort i kustomization.yaml så att bara namespace finns kvar..

- ställ dig i folder install/ kör kommando:
  
```kubectl
kustomize build . | kubectl apply -f -  
```

- ang port-forward för att komma åt gränsnitt

```kubectl
kubectl port-forward svc/argocd-server -n argocd 8085:80
```

```kubctl
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

```

```kubectl
kubectl apply -f argocd-app.yaml -n argocd

```kubectl
kubectl rollout restart -n argocd deployment argocd-repo-server

```
