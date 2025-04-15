- Each pod is assigned a cluster-wide unique IP address thanks to the CNI plugin
	- Simple communication with different pods in the cluster through direct IP address without [[Network Address Translation NAT]]
- Agents on a node (e.g. kubelet) can communicate with all pods on the node.
- IP of a pod can change (restart or any other reason), this is dangerous and not comfortable, for this reasons [[Ingress]],[[Service]] or [[StatefulSet]].

## CNI plugin
- Stands for Container Network Interface
- Binary used to assign an IP address to a pod and connect it to the cluster network
- When a pod is created, kubelet on the node triggers the CNI to:
	1. Assign a unique IP address to the pod
	2. Set up routing rules so that pod is accessible