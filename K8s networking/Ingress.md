- Layer 7 HTTP router sitting in front of one or more [[Service]]
- Routes requests based on hostnames or paths
- Consolidates external access (external requests) between one load balancer
- part of the K8s api

### Example:
![[Pasted image 20250414214246.png]]

## Controller
- The controller can be implemented by  [[NGINX]] 
- If NGINX controlled used in combination with service mesh, it is not a part of the mesh - security, policy, traffic shifting
- When you update an Ingress rules, the controller dynamically detects the change, regenerates its NGINX configuration, and applies it without requiring a pod restart. This ensures zero-downtime config updates.

# Ingress Gateway
- also L7
- this is part of service mesh [[Istio]] implemented usually as an [[Envoy Proxy]]
- Not part of the K8s API
- Also handles external traffic
- Understands **Istio traffic policies**
- Can enforce **mesh security**, telemetry, and routing rules.