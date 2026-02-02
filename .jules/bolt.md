## 2026-02-02 - Incorrect use of `crossorigin` on `preconnect` for map tiles
**Learning:** Added `crossorigin` to a `preconnect` hint for `tile.openstreetmap.org`, but Leaflet loads tiles as standard `<img>` elements without CORS. Browsers treat CORS and non-CORS connections as distinct, so the preconnect was not reused for the actual tile requests.
**Action:** Always check if a resource is fetched with CORS before adding the `crossorigin` attribute to `preconnect`. For Leaflet tiles, omit `crossorigin`.
