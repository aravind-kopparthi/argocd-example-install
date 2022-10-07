
helm repo add argo-cd https://argoproj.github.io/argo-helm
mkdir argo-cd
helm dep update argo-cd/
echo "charts/" > charts/argo-cd/.gitignore
kubectl config use-context docker-desktop 
kubectl config current-context
helm install argo-cd argo-cd -n argocd
 kubectl port-forward svc/argocd-server 8080:443 -n argocd        

 https://www.eksworkshop.com/intermediate/290_argocd/install/
 kubectl get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
 z5vErNpejRHcGJKz
helm template apps/ | kubectl apply -f -
https://www.arthurkoziel.com/setting-up-argocd-with-helm/