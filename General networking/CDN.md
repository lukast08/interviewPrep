- globally distributed network of servers that **cache and deliver content** (like images, JavaScript, HTML, videos) **closer to the end users**.
- High-level functionality:
	1.  A user requests a resource (e.g., `https://example.com/image.jpg`)
	2. The **DNS of the CDN provider** routes the request to the **closest CDN edge server**
	3. If that edge server has the file cached → it serves it immediately (low latency)
	4. If not, it **fetches it from the origin server**, stores it, and then serves it
