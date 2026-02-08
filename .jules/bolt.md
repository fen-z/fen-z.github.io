## 2025-01-24 - Optimizing Map Tile Loading
**Learning:** Modern browsers and HTTP/2 make subdomain sharding (e.g., {s}.tile.openstreetmap.org) obsolete. Using a single "naked" domain allows for better connection multiplexing and reduces overhead from multiple TCP/TLS handshakes.
**Action:** Always prefer naked domains for tile layers in Leaflet when the provider supports HTTP/2, and supplement with `preconnect` resource hints.

## 2026-02-08 - Resource Hints for Redirects
**Learning:** For pages that use `meta-refresh` redirects, adding `preconnect` and `dns-prefetch` hints for the destination domain allows the browser to begin the connection handshake while still parsing the redirect page, reducing perceived latency.
**Action:** Always add resource hints for the target domain on redirect pages.
