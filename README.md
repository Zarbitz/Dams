# ZARBITZ Dams — extracted observatory

Moved from Zarbitz/Web's dam observatory source, dashboard and scripts to establish the separate Dams repository requested for the Mac Mini architecture. The compiled static version is retained in `dist/`, with local launcher scripts at the repository root. The marketing website stays in Web.

The `dist/` build now mounts at `/dams/` through the shared UserProfile server. It receives the selected asset UUID and fetches Zarr files through the ownership-checked API. Use the account dashboard to enter the platform. The standalone dashboard remains a local inspection tool.

Frontend source is in `source/`; the existing compiled dashboard and local Python server are in `dashboard/`. See `dashboard/README.md` for the original data interpretation notes. The current server expects `data/all_dams_master.zarr`; no customer data is committed. Inspect `dashboard/server.py` as the authoritative current path configuration.

For frontend development on the Mac Mini: install Node.js 22+, run `npm ci` then `npm run build` inside `source/`. This produces `dashboard/assets` and its index page. The standalone Python server is for local inspection only and does not enforce UserProfile permissions. Do not expose it directly to the internet.

Pending: end-to-end verification with the real Mac Mini stores. The legacy viewer retains Temghar defaults and specific master-store/grid assumptions; validate those against each assigned store. Never assign a multi-customer master store to one asset. See UserProfile/MAC_MINI_RULEBOOK.md and REQUIREMENTS.md.
