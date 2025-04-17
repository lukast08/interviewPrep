## IP address
- An **IP address** is a unique identifier for a device on a network.
- **IPv4**: e.g., `192.168.1.10`
- **IPv6**: e.g., `2001:0db8:85a3::8a2e:0370:7334`
## Ports
- A **port** is a logical endpoint for network communication on a device.
- Allow a single IP to run multiple services

## TCP
- 3-way handshake (SYN, SYN-ACK, ACK) before transmitting any data
- Acknowledges receipt of data, retransmits if necessary
- Used anywhere where accuracy matters mode than speed (HTTPS, SSH, SMTP, SQL databases)

## UDP
- No connection setup, just sending packets blindly
- No retries
- Lower latency and overhead
- Used anywhere where speed matters more than accuracy (DNS Queries, Video/audio streams, online gaming, real-time messaging)

## HTTP
- HTTP (Hypertext Transfer Protocol) is an **application-layer protocol standard** defined and maintained by the **Internet Engineering Task Force (IETF)**
- HTTP methods: POST, GET, PUT, DELETE
- HTTP status codes: 2xx, 3xx, 4xx, 5xx

## OSI Model
- Splits the communication of two devices over a network into 7 abstraction layers
1. Physical layer - hardware needed for network communication
2. Data Link layer:
	- takes raw bit from physical layer and organizes them into packets
	- makes sure that the packets arrive at the correct destination
3. Network layer: 
	- Responsible for routing data across different networks
	- IP addresses, etc.
4. Transport layer: TCP, UDP
5. Application Layer: Combination of the last three. SMTP, HTTP, FTP, DNS
![[Pasted image 20250416161834.png]]
