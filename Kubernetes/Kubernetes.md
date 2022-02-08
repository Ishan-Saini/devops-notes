## What is Kubernetes?
- A container orchestration tool which helps in managing containers efficiently.
- There has been shift from monolithic architectural designs to microservices which in turn has made the containerization popular. A microservices design can consists of thousands of containers which makes it difficult for the team to manage them, this is where the Kubernetes comes to the rescue.

## What features does it offer ?
- High availibility - no downtime
- Scalibility - high performance
- Disaster recovery - backup and restore

## Kubernetes components
- **Node** - It is basically a server (physical or virtual) and contains the pods. 
- **Pod** - Smallest unit of K8s
	- Pod is just an abstraction over container. It usually contains a single container and abstracts away the functionalities of underlying container technology (like docker) so that only the kubernetes layer over it can be used.
	- Each pod has its own IP address. If by any chances any pod dies, a new pod replaces it and the IP address linked to it also changes.
	- Since the pods can die and get replaced, it is incovenient to keep track of IP addresses linked to them. That's where the service component comes in.
- **Service** - A permanent IP address that is attached to a pod.
	- Helps in communication inside the cluster.
	-  Lifecycles of pods and service are not connected, so even if a pod dies, the service and its IP address remains.
	-  External service is used to expose the application to external sources.
	-  Internal service is used for internal connections eg. database services (we don't want our database to be open to public requests)
- **Ingress** - Ingress exposes HTTP and HTTPs routes from outside the cluster to services within the cluster.
- **ConfigMap** - A ConfigMap is an API object used to store non-confidential data in key-value pairs. 
	- It can be consumed by Pods in the form of environment variables, command line arguments or as a configuration file in volume.
	- It helps in seperating the configuration information from the application code. 
	- For eg. config for database services (Not the confidential data)
- **Secret** -  It is an object that contains a small amount of sensitive data such as a password, a token or a key. Using a Secret means that you don't need to include confidential data in your application code.
- **Volumes** - Since a pod can cease to exist, the data inside it will too. To persist data of a container inside the pod we make use of volumes. Volumes makes use either the local storage or a remote storage to store the data inside the container.
- **Deployment** - 
- **StatefulSet** - 

## Kubernetes architecture
[RedHat article on K8s architecture](https://www.redhat.com/en/topics/containers/kubernetes-architecture)