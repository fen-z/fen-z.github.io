## 2026-01-31 - Vendoring Leaflet for Performance
**Learning:** Vendoring critical libraries like Leaflet.js in a static site significantly improves performance by reducing DNS lookups and TLS handshakes to third-party CDNs. It also ensures long-term reliability of the application.
**Action:** Always check for third-party scripts and styles in the critical path and consider vendoring them if they are small enough and stable.
