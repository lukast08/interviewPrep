- Kubernetes controller used to manage **stateful applications**
- Works as an alternative to deployments
- Each pods gets a persistent name, volume
	- Pods retain identity across restarts
- Good for applications that need to keep a state such as databases, message queues

### Important to know
- StatefulSet **needs a Headless Service** (`clusterIP: None`) to resolve DNS per pod
- Persistent volumes remain even if pods are deleted or scaled down