# Kubernetes building blocks, e.g. Pods, ReplicaSets, Labels, Deployments, rolling updates

## Learning Resources

-> Linux Foundation : chapter 8 Kubernetes building blocks

Definitions of Pods, ReplicaSets, Deployments

Hands-on : rolling update and rollback 

```
kubectl create deployment mynginx --image=nginx: 1.15-alpine

kubectl get deploy,rs,po -l app=myngnix //short version

kubectl scale deploy mynginx --replicas=3

kubectl rollout history deployment mynginx (optionnal --revision=1)

kubectl set image deployment mynginx nginx=nginx:1.16-alpine

kubectl rollout undo deployment mynginx --to-revision=1'
```

### Pods

A Pod is the smallest and simplest Kubernetes object. It is the unit of deployment in Kubernetes, which represents a single instance of the application. A Pod is a logical collection of one or more containers, which:

Are scheduled together on the same host with the Pod
Share the same network namespace, meaning that they share a single IP address originally assigned to the Pod
Have access to mount the same external storage (volumes).

### Labels

Labels are key-value pairs attached to Kubernetes objects (e.g. Pods, ReplicaSets, Nodes, Namespaces, Persistent Volumes). Labels are used to organize and select a subset of objects, based on the requirements in place. Many objects can have the same Label(s). Labels do not provide uniqueness to objects. Controllers use Labels to logically group together decoupled objects, rather than using objects' names or IDs.

### Deployments

Deployment objects provide declarative updates to Pods and ReplicaSets. The DeploymentController is part of the master node's controller manager, and as a controller it also ensures that the current state always matches the desired state. It allows for seamless application updates and rollbacks through rollouts and rollbacks, and it directly manages its ReplicaSets for application scaling. 

A rolling update is triggered when we update specific properties of the Pod Template for a deployment. While updating the container image, container port, volumes, and mounts would trigger a new Revision, other operations like scaling or labeling the deployment do not trigger a rolling update, thus do not change the Revision number.

However, the Deployment keeps its prior configuration states saved as Revisions which play a key factor in the rollback capability of the Deployment - returning to a prior known configuration state.

### ReplicatSets

With the help of a ReplicaSet, we can scale the number of Pods running a specific application container image. Scaling can be accomplished manually or through the use of an autoscaler.
