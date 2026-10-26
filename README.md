# 317MX — redesigned website

Open **index.html** after extracting this entire ZIP. Keep index.html, styles.css, app.js and assets together. This is a simple static site: no build tools, database, PHP, live-status bridge or MX restart needed.

The page contains your supplied 18-track lineup, original images downloaded from each forum topic, regenerated wood/logo/peace artwork, your riding photos, section navigation, image enlargement, copy-address buttons and your Discord invite. The old slogans and live-roster section are removed for this version. The displayed lineup follows your supplied list; no game-server rotation was edited or verified.

## Publish when ready

- **GitHub Pages:** upload index.html, styles.css, app.js, .nojekyll and the assets directory to the repository root. Settings → Pages → Deploy from branch → main / root. Keep 317mx.duckdns.org pointing to your droplet, not GitHub Pages, if you want the same hostname for the game.
- **Droplet:** copy those same files into the new site's document root `/var/www/317mx/`. Use the previous deployment guide for the separate Nginx hostname and HTTPS setup, but skip its bridge/exporter sections. This redesign makes no `/api/status` requests. A static-only Nginx site needs only the document root, index, try_files and certificate configuration.
- No deployment has been performed. Divinity, MX systemd, credentials and track rotation remain untouched.

## Editing

Track cards are ordinary HTML in index.html. Each card has its image, title and forum URL together. Edit them directly; tracks.json records the source mapping for reference and is not loaded dynamically. All download buttons open the forum topics, not an invented direct download. Hidden Acres uses the logo actually supplied by its forum post. Click a track image for the full original, including collages.

The wood is fixed behind the page so it has no repeating horizontal seams. Change animation styling in styles.css; the MOTION button pauses it, and reduced-motion system preferences are respected. Fonts use Google Fonts (Permanent Marker and Barlow Condensed) with local fallback fonts if offline. All photos and branding are local files. Original full-resolution track assets are retained, so the ZIP is relatively large; track images load lazily.

## Generated artwork

Built-in image generation was used with these prompts and the three supplied references:

1. Wood: regenerate the reference as an evenly illuminated seamless dark walnut vertical cabin-plank texture; natural grain, flat straight-on, no vignette, spotlight, objects or text; matching edges.
2. Logo: one isolated transparent 317MX graffiti mark, preserving irregular chunky lettering, green-yellow-red gradient, worn gold outline and dark carved edges; no extra text, fence or duplicates.
3. Peace: isolated transparent rough brush-painted peace sign, green left, yellow center, red right, with distressed organic strokes; no background or lettering.

Assets: `assets/wood.png`, `assets/logo.png`, `assets/peace.png`. Original riding photos and forum imagery were not regenerated.
