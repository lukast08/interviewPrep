- distributes the traffic across all available pods
- L4 (TCP - iptables, etc.) or L7 (application - software (HTTP) load balancer) layers.
	- L4 is fast, simple but could has no insight into the app context
	- L7 is smarter, finer control. Could have higher complexity than L4

## K8s load balancing

### Services LB
- round robin by default
- K8s services use L4 load balancin on `ClusterIP` type
- K8s `LoadBalancer` service could use both L4 and L7
- due to L4 no knowledge about the app

### Service mesh LB
- L7
- handled by the proxy (e.g. [[Envoy Proxy]])
- Intelligent routing base on:
	- URL, paths
	- Service version or labels
	- Real-time health of the pods
	- A/B testing of services
- Could do retries, failovers, circuit breaking
- Gathers metrics and logs
- **Load balances the traffic directly to a concrete pod thanks to a list of all healthy pods IP addresses behind another service thanks to control plane**


### Other types
#### External LBs
- Served by the cloud platforms
- Often used in front of [[Ingress]] controllers or ingress gateways

#### DNS load balancing (L3)
- special case of load balancing in L3
- uses DNS responses to rotate IPs using RR
- very simple (no health checking, etc)

#### Global LB
- routes traffic based on region