Step-by-Step Instructions

Install ArgoCD

'''
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
'''

Expose the ArgoCD API Server:
''' kubectl port-forward svc/argocd-server -n argocd 8080:443 ''' 

Access ArgoCD at: https://localhost:8080


Get the initial password (the pod name of argocd-server):
''' kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d'''