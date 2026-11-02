# ZARBITZ Dams — extracted observatory

Moved from Zarbitz/Web's dam observatory source, dashboard and scripts to establish the separate Dams repository requested for the Mac Mini architecture. The compiled static version is retained in `dist/`, with local launcher scripts at the repository root. The marketing website stays in Web.

This is a work-in-progress extraction, not a completed shared-account integration. The existing dashboard still expects root-relative assets and Zarr paths and is not yet ready to mount at `/dams/`.

Frontend source is in `source/`; the existing compiled dashboard and local Python server are in `dashboard/`. See `dashboard/README.md` for the original data interpretation notes. The current server expects `data/all_dams_master.zarr`; no customer data is committed. Inspect `dashboard/server.py` as the authoritative current path configuration.

For frontend development on the Mac Mini: install Node.js 22+, run `npm ci` then `npm run build` inside `source/`. This produces `dashboard/assets` and its index page. The standalone Python server is for local inspection only and does not enforce UserProfile permissions. Do not expose it directly to the internet.

Pending: authenticated asset selection, per-asset dataset routing, consolidated deployment configuration and end-to-end verification.
