- A way to expose an application running on a set of pods as a network service
- Ensures that is a pod IP changes, the other things can still communicate with it
- Four types:
	- **ClusterIP**: Default. Exposes service on an internal IP in the cluster, Internal communication (e.g., frontend → backend), Internal only
	- **NodePort**: Exposes the service on a static port on each Node's IP|Basic external access without cloud LoadBalancer|External IP of any node|
	- **LoadBalancer**: Provisions a cloud provider load balancer and forwards traffic|Production-level public access in cloud|External traffic|
	- |**ExternalName**: Maps service to an external DNS name|Access external services via internal DNS|Outside Kubernetes|

