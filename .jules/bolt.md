## 2025-01-24 - Optimizing Map Tile Loading
**Learning:** Modern browsers and HTTP/2 make subdomain sharding (e.g., {s}.tile.openstreetmap.org) obsolete. Using a single "naked" domain allows for better connection multiplexing and reduces overhead from multiple TCP/TLS handshakes.
**Action:** Always prefer naked domains for tile layers in Leaflet when the provider supports HTTP/2, and supplement with `preconnect` resource hints.
