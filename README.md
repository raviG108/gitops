Step-by-Step Instructions




kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


kubectl get pods -n argocd

kubectl get svc -n argocd


kubectl edit svc argocd-server -n argocd  //EDITOR=nano kubectl edit svc argocd-server -n argocd

 
 change the ClusterIp to  NodePort
 
 
 minikube service list -n argocd 
 
 minikube service argocd-server -n argocd // show the ip address 


username is admin
for password 
kubectl get secret -n argocd    

EDITOR=nano kubectl edit secret argocd-initial-admin-secret -n argocd 
this is the pass Qm5VQ0UyZ2ZMYlZJeEE3YQ==

now need to decode it 

echo Qm5VQ0UyZ2ZMYlZJeEE3YQ== | base64 --decode     //BnUCE2gfLbVIxA7a
