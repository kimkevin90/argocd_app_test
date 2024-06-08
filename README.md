https://github.com/SMACAcademy/ArgoCD-Complete-Master-Course/blob/main/1-Installation_and_Setup/3-Access_ArgoCD_with_NodePort.md

kubectl config set-context --current --namespace=argocd

argocd admin initial-password
argocd login localhost:8080

minikube service argocd-server --url -n argocd


### Creating Apps Via CLI
kubectl config set-context --current --namespace=argocd

minikube service --all -n argocd

argocd admin initial-password -n argocd

argocd login 192.168.49.2:30443

argocd app create guestbookcli --repo https://github.com/kimkevin90/argocd_app_test.git --path guestbook --dest-server https://kubernetes.default.svc --dest-namespace default

argocd app sync guestbookcli

argocd app delete guestbookcli