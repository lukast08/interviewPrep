- Solution for managing communication between microservices **securely**
- Provides features such as:
	- Traffic spliting, routing, balancing
	- Observability
	- **Security**
	- Reliability (retries, timeouts, circuit breakers)
	- **Instead of the service worrying about these features, service mesh abstracts them into the platform**

- Without SM, there is usually security before the cluster (like a firewall) but once request is inside the cluster, the components communicate through HTTP. Service mesh adds the security

## Architecture

### Control plane
- Manages and configures the data plane
- Handles service discovery, configuration updates, certificate distribution, etc.
### Data plane
- One for each pod
- Actually handles traffic
- Consists of sidecar containers - proxies (envoy-proxy ve webxp-api)
- These proxy sidecars intercept all incoming traffic for the pod using `iptable` redurection

## 🔄 How It Works (Simplified Flow)

1. **Pod A wants to call Pod B.**
2. The request from Pod A is intercepted by its local sidecar.
3. The sidecar checks routing rules and security policies.
4. It forwards the request to Pod B’s sidecar.
5. Pod B’s sidecar forwards the request to the actual Pod B application.

Throughout this flow, the service mesh can:
- **Encrypt** the communication (mTLS).
- **Collect telemetry** data.
- **Retry** failed requests or **shift traffic** based on version.


**Control plane** often implemented through [[Istio]], **data plane** often uses [[Envoy Proxy]]