- translates **human-readable names** (like `google.com`) into **IP addresses** (like `142.250.190.14`)
- Uses UDP (rarely TCP for bigger responses)

- After domain was entered into a browser:
	- **Check local DNS cache** (browser or OS)
	- If not cached, query **configured DNS resolver** (e.g., `8.8.8.8`)
	- That resolver does the heavy lifting:
	    - Queries **Root Server** → server for a specific suffix (e.g. `.com`)
	    - TLD server → gives Authoritative server for `example.com`
	    - Authoritative DNS → returns the IP (e.g., `93.184.216.34`)

### DNS record types
- **A** Domain to IPv4
- **AAAA** Domain to IPv6
- **CNAME** Alias for other domain `www.example.com → example.com`
- **PTR** Reverse DNS (IP -> Domain) `93.184.216.34 → example.com`

### K8s DNS
- K8s has its own DNS system (usually CoreDNS) for service discovery
- Every pod and service gets a DNS entry
- Then I can use just `my-service` inside the same namespace and CoreDNS will resolve it
	- Doesn't know to look to other namespaces if I do not tell it. 
	- Can specify a fully qualified name to fix `my-service.other-namespace`