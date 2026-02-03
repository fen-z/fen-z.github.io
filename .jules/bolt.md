## 2026-02-03 - Avoid domain sharding in HTTP/2
**Learning:** Domain sharding (e.g., using a, b, c subdomains for tiles) is an optimization for HTTP/1.1 that becomes an anti-pattern in HTTP/2. In HTTP/2, connection multiplexing is more efficient when using a single domain, as it avoids the overhead of multiple TCP/TLS handshakes.
**Action:** Always prefer naked domains or a single subdomain for assets when the server supports HTTP/2.
