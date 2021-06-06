# Deploying a Stand-Alone Application

## Resources used

-> Linux Foundation Course

Chapter 11. Deploying a Stand-Alone Application

- Deploying an app from the minikube Dashboard using the form
- Deploying an app from the cli by creating a deploymment yaml file and then executing the command : 

```
kubectl create -f file.yaml
```
- Exposing a service with the command : 

```
kubectl expose deployment webserver --name=webservice --type=NodePort
```

also some theory about liveness & readiness probes

### Readiness probes

Sometimes, while initializing, applications have to meet certain conditions before they become ready to serve traffic. These conditions include ensuring that the depending service is ready, or acknowledging that a large dataset needs to be loaded, etc. In such cases, we use Readiness Probes and wait for a certain condition to occur. Only then, the application can serve traffic.

A Pod with containers that do not report ready status will not receive traffic from Kubernetes Services.

### Liveness probes

If a container in the Pod has been running successfully for a while, but the application running inside this container suddenly stopped responding to our requests, then that container is no longer useful to us. This kind of situation can occur, for example, due to application deadlock or memory pressure. In such a case, it is recommended to restart the container to make the application available.

Rather than restarting it manually, we can use a Liveness Probe. Liveness probe checks on an application's health, and if the health check fails, kubelet restarts the affected container automatically.

Liveness Probes can be set by defining:

- Liveness command
- Liveness HTTP request
- TCP Liveness probe. 
