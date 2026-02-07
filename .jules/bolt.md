## 2025-01-24 - Optimizing Map Tile Loading
**Learning:** Modern browsers and HTTP/2 make subdomain sharding (e.g., {s}.tile.openstreetmap.org) obsolete. Using a single "naked" domain allows for better connection multiplexing and reduces overhead from multiple TCP/TLS handshakes.
**Action:** Always prefer naked domains for tile layers in Leaflet when the provider supports HTTP/2, and supplement with `preconnect` resource hints.

## 2026-02-07 - Optimizing Redirects with Resource Hints
**Learning:** For pages that serve as immediate redirects (meta-refresh), preconnecting to the destination domain can significantly reduce the "white screen" time by performing DNS/TCP/TLS handshakes while the browser is still parsing the redirect instruction. Adding these hints to the *referring* page (where the user clicks the link) provides even greater speculative performance gains.
**Action:** Use `preconnect` and `dns-prefetch` for external redirect destinations on both the redirect page itself and any primary referring pages.
