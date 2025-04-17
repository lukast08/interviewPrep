- Server that acts as a **central entry point** for all client requests to a backend system or group of microservices
- Handles things like: rate limiting, IP whitelisting, routing, monitoring, caching, payload compression/transformation/validation
- Compared to [[Load balancing]], it can also do it. But its responsibilities are a bit different. Typical load balancers are faster as they only route traffic, API Gateway is also responsible for - **Authentication/authorization**, **Rate limiting / quotas**, **Request/response transformations**, **Logging and monitoring**
	- Similar to ingress, more feature rich

[[Istio]], [[NGINX]], [[Envoy Proxy]] can be used as API Gateways