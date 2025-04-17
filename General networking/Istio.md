- [[Service Mesh]] control plane
- Consists of:
	- [[Envoy Proxy]] in the data planes
	- Pilot: Pushes config (e.g., routing rules) to envoy proxies
	- Istiod: core control plane that manages configuration, service discovery, and security for the data plane proxies. It distributes routing policies, updates, and TLS certs to the Envoy sidecars.

- Could be used as Ingress controller thanks to Istio Ingress Gateway
	- External traffic enters through the Istio Ingress Gateway, which applies mesh policies like routing, auth, and telemetry. From there, traffic is routed to internal services through their Envoy proxies.


## The Flow in Istio:

1. **Request hits Envoy sidecar** (from app or Ingress).
2. Envoy uses the **VirtualService** to determine:
    - Which **host** to send the request to
    - Which **subset/version** to send it to
    - Based on things like path, headers, or weight
3. Envoy looks up the **DestinationRule** for that destination:
    - Applies **load balancing policy** (round-robin, least request, etc.)
    - Applies **circuit breaking**, **TLS**, and other policies
4. Traffic is forwarded to one of the **actual pods** behind that subset.