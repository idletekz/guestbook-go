```bash
k apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.3.1/deploy/static/provider/cloud/deploy.yaml

kubectl create ingress guestbook-ingress --class=nginx --rule /=guestbook:3000 --dry-run=client -o yaml > ingress.yml
```