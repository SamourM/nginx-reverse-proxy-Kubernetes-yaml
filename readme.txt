launcing

gcloud container clusters create forbes-nginxx \
 --num-nodes=3 --zone us-central1-a --machine-type=custom-2-12288
============================

resizing

gcloud container clusters resize forbes-nginxx --size=0 --zone us-central1-a
===============================

gcloud compute firewall-rules create your-name-for-this-fw-rule --allow tcp:80,tcp:443 --source-ranges=0.0.0.0/0

=========================================







https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html   local repo push.

==================================================



https://github.com/kubernetes/kompose kompose installation 


=====================================================

you need to route external traffic to the service.
basic ingress:

apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: basic-ingres
spec:
  backend:
    serviceName: rev-proxy
    servicePort: 80

========================================


kubectl get ing >> get cluster IP.
kubectl get pods
kubectl get nodes
===============


*****************
this is very fff******* important:


To expose k8s service, after deployng deployment and service, please:

make sure you added type: Nodeport on service.yaml

apply basic-ingress.yaml

note:: apply the deployment then the service then the ingree 



or
 instead all of above do this one command:

kubectl expose deployment mysql --port 3306 --target-port 3307 --type="LoadBalancer"


gcloud compute firewall-rules create your-name-for-this-fw-rule --allow tcp:80,tcp:443 --source-ranges=0.0.0.0/0

*******************
