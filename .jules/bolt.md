## 2026-02-01 - Leaflet Domain Optimization
**Learning:** For Leaflet tile layers, using the naked domain `https://tile.openstreetmap.org` instead of subdomains like `{s}.tile...` is preferred in HTTP/2 environments. This allows better utilization of connection multiplexing and avoids multiple TCP/TLS handshakes.
**Action:** Always prefer the naked domain for OSM tiles when performance is a priority and the server supports HTTP/2.
