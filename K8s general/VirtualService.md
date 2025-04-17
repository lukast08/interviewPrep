- is an [[Istio]] custom K8s resource
- defines how requests are routed to its service
- K8s service uses L4 routing - very simple
	- VirtualService allows me to define powerful L7 routing rules - traffic splitting, retries, etc.
- Allows to:
	- route traffic to different versions of a service
	- Do canary deployments, A/B testing
	- Apply specific conditions based on HTTP headers, URIs, methods, etc.
- Difference between Virtual and vanilla service:
	- **K8s service** resolves service name to pods IPs (L4)
	- **Virtual service** applies L7 routing on top of basic K8s service routing
- Traffic still goes through the **Kubernetes Service**, but Istio's **Envoy proxies** (sidecars) use the **VirtualService rules** to decide **how to handle and route the traffic**.

# DestinationRule
- declared as part of [[VirtualService]]
- defines how the traffic is balanced once it is at the destination