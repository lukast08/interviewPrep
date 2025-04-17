- K8s object managing and automating lifecycle of a set of replicated PODs
- Can run multiple containers
- Makes sure that:
	- A desired n of replicas are running
	- Automatic rollbacks and updates are possible

- Creates and manages [[ReplicaSets]]  
- Allows zero-downtime rolling updates:
```
strategy:  
  type: RollingUpdate  
  rollingUpdate:  
    maxSurge: 1  
    maxUnavailable: 0
```