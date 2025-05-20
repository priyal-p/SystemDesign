<h1>🔧 What is a Front-End (Reverse) Proxy?</h1>

A reverse proxy like NGINX:
<ul>
<li>Accepts client (e.g., browser) requests.

<li>Forwards them to backend servers (e.g., Node.js, Python, PHP, etc.).

<li>Returns the backend's response to the client.
</ul>

✅ Benefits of Using NGINX as a Front-End Proxy
<ul>
<li> Load Balancing - 
Distribute traffic across multiple backend servers for high availability and performance.

<li> SSL Termination - 
Handle HTTPS traffic at the NGINX layer to offload SSL workload from backend servers.

<li> Security - 
Hide backend infrastructure, block malicious requests, set rate limits, and filter headers.

<li> Caching - 
Cache static content or API responses to reduce backend load.

<li> Compression - 
Serve compressed (gzip, Brotli) responses to clients, speeding up page loads.

<li> Static File Serving - 
Efficiently serve assets like images, CSS, and JS directly from NGINX.
<ul>

🧪 Tips
 - Always test changes with `nginx -t` before reloading.

- Use `proxy_cache` for caching dynamic content.

- Use location `/api/` and location `/static/` blocks to route specific traffic differently.
