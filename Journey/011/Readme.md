# Ingress + refresh memory on Pods, Deployments and Services
## Learning material

--> Linux Foundation : chapter 14 : Ingress

With Services, routing rules are associated with a given Service. They exist for as long as the Service exists, and there are many rules because there are many Services in the cluster. If we can somehow decouple the routing rules from the application and centralize the rules management, we can then update our application without worrying about its external access. This can be done using the Ingress resource. 

According to kubernetes.io,

"An Ingress is a collection of rules that allow inbound connections to reach the cluster Services."

To allow the inbound connection to reach the cluster Services, Ingress configures a Layer 7 HTTP/HTTPS load balancer for Services and provides the following:

TLS (Transport Layer Security)
Name-based virtual hosting 
Fanout routing
Loadbalancing
Custom rules.
 
An Ingress Controller is an application watching the Master Node's API server for changes in the Ingress resources and updates the Layer 7 Load Balancer accordingly. Ingress Controllers are also know as Controllers, Ingress Proxy, Service Proxy, Revers Proxy, etc. Kubernetes supports an array of Ingress Controllers, and, if needed, we can also build our own. GCE L7 Load Balancer Controller and Nginx Ingress Controller are commonly used Ingress Controllers. Other controllers are Contour, HAProxy Ingress, Istio, Kong, Traefik, etc.

Start the Ingress Controller with Minikube

Minikube ships with the Nginx Ingress Controller setup as an addon, disabled by default. It can be easily enabled by running the following command:

$ minikube addons enable ingress 

---> Understanding K8s in a visual way Youtube : 1/2/3
Pods
Deployments
Services
