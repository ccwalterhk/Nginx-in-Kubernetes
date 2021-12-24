# Nginx-in-Kubernetes
Deployment of Nginx load balancer in Kubernetes


This is an example of NGX load balancer deployment in K8s.
The load balancer configuration stores externally in NFS persistent volume.
PV, PVC and service node port is configured inside the .yaml file.


The directory "ngx-config" stores sample configuration of ngx load balancer.
It should be mounted to /etc/nginx in nginx container image.

nginx.conf inside "ngx-config" directory is the actual configuration file.


Configuration in nginx.conf defines the listening port. TCP/9090 is set as example.
Traffic to the TCP port 9090 will be forwarded to upstream. 
The upstream is named as "stream_backend_netbox_HTTP_9090"
In the upstream session, it defines the real server. 
The real server can be defined either using IP address or FQDN.  
In this example, FQDN - netbox.home.local is used. 
