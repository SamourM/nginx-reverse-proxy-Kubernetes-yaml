*Launching a cluster on GCP:

gcloud container clusters create forbes-nginxx \
 --num-nodes=3 --zone us-central1-a --machine-type=custom-2-12288
===========================================================================================================

*Resizing a cluster on GCP:

gcloud container clusters resize forbes-nginxx --size=0 --zone us-central1-a
===========================================================================================================

*Adding Firewall rule to allow traffic from outside.

gcloud compute firewall-rules create your-name-for-this-fw-rule --allow tcp:80,tcp:443 --source-ranges=0.0.0.0/0

===========================================================================================================

*Push to docker hub

https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html   local repo push.

==================================================
*kompose installation 


https://github.com/kubernetes/kompose 

=====================================================

you need to route external traffic to the service, write a basic ingress. (not the best practice though).
basic ingress:

apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: basic-ingres
spec:
  backend:
    serviceName: rev-proxy
    servicePort: 80

===================================================================================================

*To expose k8s service, after deployng deployment and service, please:

*make sure you added type: Nodeport on service.yaml

*apply basic-ingress.yaml

*note: apply the deployment then the service then the ingree 

*gcloud compute firewall-rules create your-name-for-this-fw-rule --allow tcp:80,tcp:443 --source-ranges=0.0.0.0/0

or

*instead all of above apply this one command:

********   kubectl expose deployment mysql --port 3306 --target-port 3307 --type="LoadBalancer"  ********


===========================================================================================================

*Get cluster IP

kubectl get ing >> get cluster IP.


=========================================================



PHP FastCGI Process Manager (PHP-FPM) is an alternative FastCGI daemon for PHP that allows a website to handle high loads. 

=========================================================


Supervisord or Supervisor daemon is an open source process management system. In a nutshell: if a process crashes for any reason, Supervisor restarts it. From the Supervisord website:[1] 
=========================================================



https://github.com/makasim/docker-nginx-php-fpm-supervisor

=========================================================


When using the Nginx web server, you can use server blocks (similar to virtual hosts in Apache) to encapsulate configuration details and host more than one domain from a single server.

=========================================================


Nginx is not able to talk to PHP directly but through FPM protocol so we also have to run PHP-FPM service

=========================================================

https://websiteforstudents.com/install-wordpress-4-9-on-ubuntu-17-04-7-10-with-nginx-mariadb-and-php/


========================================================

Start Here:

https://websiteforstudents.com/install-nginx-mariadb-php-fpm-lemp-ubuntu-17-10/

https://websiteforstudents.com/install-wordpress-4-9-on-ubuntu-17-04-7-10-with-nginx-mariadb-and-php/

https://luoluca.wordpress.com/2015/01/07/hosting-php-nginx-supervisor-with-docker/

========================================================================================================================


