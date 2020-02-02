Nginx - Ingress controller must be configured before this.

The domains apache.sadhana.com and nginx.sadhana.com must be registered with the LoadBalancer, which is mapped to Nginx's service (LB-svc).

kubectl commands, without execting the yamls
--------------------------------------------
kubectl create deploy nginx --image=nginx
kubectl create deploy apache --image=httpd
kubectl expose deploy apache --name=apache-svc --port=80 
kubectl expose deploy nginx --name=nginx-svc --port=80 
kubectl apply -f nginx.yaml
