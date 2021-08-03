# Introduction to autoscaling

While it is fairly easy to manually scale a few Kubernetes objects, this may not be a practical solution for a production-ready cluster where hundreds or thousands of objects are deployed. We need a dynamic scaling solution which adds or removes objects from the cluster based on resource utilization, availability, and requirements. 

Autoscaling can be implemented in a Kubernetes cluster via controllers which periodically adjust the number of running objects based on single, multiple, or custom metrics. There are various types of autoscalers available in Kubernetes which can be implemented individually or combined for a more robust autoscaling solution:

Horizontal Pod Autoscaler (HPA)
HPA is an algorithm-based controller API resource which automatically adjusts the number of replicas in a ReplicaSet, Deployment or Replication Controller based on CPU utilization.

Vertical Pod Autoscaler (VPA)
VPA automatically sets Container resource requirements (CPU and memory) in a Pod and dynamically adjusts them in runtime, based on historical utilization data, current resource availability and real-time events.

Cluster Autoscaler
Cluster Autoscaler automatically re-sizes the Kubernetes cluster when there are insufficient resources available for new Pods expecting to be scheduled or when there are underutilized nodes in the cluster.
