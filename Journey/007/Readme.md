# Services

## Learning Resources

-> Linux Foundation : Chapter 10 -> Services

Kubernetes provides a higher-level abstraction called Service, which logically groups Pods and defines a policy to access them. This grouping is achieved via Labels and Selectors.
Labels and Selectors use a key/value pair format.
Services can expose single Pods, ReplicaSets, Deployments, DaemonSets, and StatefulSets.

While defining a Service, we can also choose its access scope. We can decide whether the Service:

Is only accessible within the cluster
Is accessible from within the cluster and the external world
Maps to an entity which resides either inside or outside the cluster.
Access scope is decided by ServiceType property, defined when creating the Service. 
ClusterIP is the default ServiceType. A Service receives a Virtual IP address, known as its ClusterIP. This Virtual IP address is used for communicating with the Service and is accessible only from within the cluster. 

With the NodePort ServiceType, in addition to a ClusterIP, a high-port, dynamically picked from the default range 30000-32767, is mapped to the respective Service, from all the worker nodes.

The NodePort ServiceType is useful when we want to make our Services accessible from the external world. The end-user connects to any worker node on the specified high-port, which proxies the request internally to the ClusterIP of the Service, then the request is forwarded to the applications running inside the cluster. Let's not forget that the Service is load balancing such requests, and only forwards the request to one of the Pods running the desired application. To manage access to multiple application Services from the external world, administrators can configure a reverse proxy - an ingress, and define rules that target specific Services within the cluster. 
