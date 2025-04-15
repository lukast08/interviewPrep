- Works on layer 3 of the OSI model
- Allows private IPs to access internet and routes the traffic back to a specific IP

### Example:
Outbound:
1. A pod with IP 10.0.0.12 makes a HTTP request to example.com
2. The NAT gateway replaces the **source IP** `10.0.0.12` with the **public IP** of the NAT device (e.g., `3.91.20.55`).
3. Response from `example.com` comes back to `3.91.20.55`, and NAT translates it back to `10.0.0.12`
Inbound:
- A public IP (`52.90.20.33`) receives a request on port `443`.
- A LoadBalancer or Ingress controller uses DNAT to rewrite the **destination IP** to an internal service or pod (e.g., `10.0.2.5`).
- The service receives the traffic and responds back through the NAT path.

In the context of K8s, services of type LoadBalancer or Ingress rely on Inbound

While NAT isn’t a standalone program, it’s implemented by:
- **Routers** (home or cloud)
- **Firewalls** (e.g., AWS Security Appliances)
- **Linux iptables / nftables** (at OS level)
- **Kube-proxy** in Kubernetes (for some traffic)
- **Cloud NAT Gateways** (like AWS NAT Gateway)