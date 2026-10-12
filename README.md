# Hound Dogs — website

Static bilingual site for hound-dogs.rs. Serbian Latin is the default; SR/EN preference is remembered.

## Publish
Upload the **contents of this folder** to your web root (or to a GitHub Pages repository). Set your custom domain to `hound-dogs.rs` in your hosting settings. HTTPS/DNS must be configured separately.

**Local preview:** Double-click `index.html` to preview without a server. The bundled content is used automatically for local file previews. For a live preview of changes to JSON, run `python3 -m http.server 8000` in this folder and visit http://localhost:8000/.

## Update the next show
1. Upload a JPEG/PNG/WebP poster to `assets/posters/` (WebP recommended, about 100–250 KB).
2. Edit `data/shows.json` — set `poster` to e.g. `assets/posters/dublin-pub-2026-10-17.webp`.
3. Update `date` (YYYY-MM-DD), `venue`, `city`, `time` (24-hour HH:MM), and optional `eventUrl`.
4. Commit/publish.
Only one show is displayed. After the date passes, the site hides the show and displays a neutral message. If the show starts after midnight, edit the date logic to match your policy. Empty city/time values are allowed.

## Update videos
Edit `data/videos.json` and paste YouTube's 11-character ID from each URL in `youtubeId`. The first video is first on the page. Video players load only on click. Titles are currently generic because original video titles have not been verified.

## Update bio, contact, social links and rider
Edit `data/content.json`. The `sr` and `en` entries hold both languages. Both homepage and `/booking/` read this same file.

## Pending
- Dublin Pub show city and start time (2026-10-17). Poster is already included.
- Downloadable press photos and final stage plot/rider PDF.
- Verify video titles and change generic titles in videos.json.
- Exact Artick font: not included; supply licensed webfont if you want it. Current logo uses Bebas Neue via Google Fonts and the tagline uses a serif fallback.
- The technical rider is a summary of the supplied requirements, not a complete stage plot/input list.

## Privacy and performance
No tracking scripts or cookies are added by the site. The language preference uses localStorage. Google Fonts and YouTube thumbnail images are third-party resources; YouTube embeds load on click. You may self-host a properly licensed font for greater privacy/performance.

**Important:** The HTML contains an embedded fallback snapshot of the JSON for offline/file previews. On a hosted website, JSON files are fetched fresh and remain the source of truth. For an updated offline preview after editing JSON, run the local server instead or regenerate the embedded snapshot.

## Contact privacy
Public booking contact is email and Instagram only. Phone number has been removed from website content and embedded fallback data. Note: previous Git commits may still contain it in repository history.

## Poster preview
The included HTML fallback has been synchronized with `data/shows.json`, including the Dublin Pub poster. For future updates, use `python3 -m http.server 8000` to preview the current JSON, because opening the HTML directly uses the embedded snapshot.
