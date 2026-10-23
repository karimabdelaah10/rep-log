# سجل التمرين (Rep Log) — standalone

Static PWA: `index.html`, `manifest.webmanifest`, `sw.js`, icons. No build step, no backend.
Data is stored on the device (localStorage). Use Settings → Export/Import for backups.

Must be served over HTTPS (service worker + install). Any static host works:

- **GitHub Pages:** new repo → upload these files to the root → Settings → Pages → Deploy from branch `main` / root.
- **Nginx:** copy the folder to e.g. `/var/www/gym`, add a server block for a subdomain, then `certbot --nginx -d gym.example.com`.
  Serve `sw.js` with `Cache-Control: no-cache` so updates roll out.

To ship an update: replace `index.html` and bump `CACHE` in `sw.js` (e.g. `rep-log-v2`).
