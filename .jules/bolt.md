## 2026-02-03 - Avoid domain sharding in HTTP/2
**Learning:** Domain sharding (e.g., using a, b, c subdomains for tiles) is an optimization for HTTP/1.1 that becomes an anti-pattern in HTTP/2. In HTTP/2, connection multiplexing is more efficient when using a single domain, as it avoids the overhead of multiple TCP/TLS handshakes.
**Action:** Always prefer naked domains or a single subdomain for assets when the server supports HTTP/2.

## 2026-02-03 - Vendoring Leaflet assets
**Learning:** Leaflet requires specific image assets (like marker-shadow.png) that are NOT always explicitly referenced in the CSS via `url()`. They are loaded dynamically by the JS. Missing these assets causes broken markers.
**Action:** When vendoring Leaflet, manually ensure all assets in the `dist/images` folder are downloaded to a local `images/` directory relative to the CSS/JS.
