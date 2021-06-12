# Kubernetes volume management

## Learning material

---> Linux foundation course chapter 12

In today's business model, data is the most precious asset for many startups and enterprises. In a Kubernetes cluster, containers in Pods can be either data producers, data consumers, or both. While some container data is expected to be transient and is not expected to outlive a Pod, other forms of data must outlive the Pod in order to be aggregated and possibly loaded into analytics engines. Kubernetes must provide storage resources in order to provide data to be consumed by containers or to store data produced by containers. Kubernetes uses Volumes of several types and a few other forms of storage resources for container data management. In this chapter, we will talk about PersistentVolume and PersistentVolumeClaim objects, which help us attach persistent storage Volumes to Pods. 
