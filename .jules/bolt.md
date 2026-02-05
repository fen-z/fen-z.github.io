## 2025-01-24 - Optimizing Map Tile Loading
**Learning:** Modern browsers and HTTP/2 make subdomain sharding (e.g., {s}.tile.openstreetmap.org) obsolete. Using a single "naked" domain allows for better connection multiplexing and reduces overhead from multiple TCP/TLS handshakes.
**Action:** Always prefer naked domains for tile layers in Leaflet when the provider supports HTTP/2, and supplement with `preconnect` resource hints.

## 2026-02-05 - Vendoring CDN Assets
**Learning:** For critical libraries like Leaflet, vendoring assets (JS, CSS, images) eliminates cross-origin overhead (DNS, TCP, TLS) and improves reliability. When vendoring, it's essential to include all images referenced by the CSS and the source map to avoid 404s in dev tools.
**Action:** Identify critical third-party dependencies and vendor them locally to consolidate origins and speed up cold loads.
