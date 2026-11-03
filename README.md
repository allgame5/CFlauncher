# Web Assets Ordner

Dieser Ordner enthält alle Dateien, die über den Webserver für den Launcher bereitgestellt werden.

## Struktur

```
web/
├── distribution.json      # Launcher-Distribution (wird vom Launcher geladen)
├── rss.xml                # News-Feed für den Launcher
├── icon.png               # Server-Icon (512x512 empfohlen)
├── assets/
│   ├── helios_small.png   # Discord Small Image (32x32)
│   ├── mein_server_large.png   # Discord Large Image (512x512)
│   └── mein_fabric_large.png   # Discord Large Image für Fabric
├── mods/
│   └── (deine Mod-JARs hier ablegen)
└── resourcepacks/
    └── (deine Resource Packs hier ablegen)
```

## Deployment

Lade den gesamten `web/` Ordner auf deinen Webserver hoch (Nginx, Apache, GitHub Pages, Netlify, Vercel, etc.).

Wichtig: Setze CORS-Headers, damit der Launcher die Dateien laden kann:
```
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET, HEAD
Access-Control-Allow-Headers: Content-Type
```

## URLs in distribution.json

Nach dem Deployment aktualisiere die URLs in `distribution.json` auf deine Domain:

```json
"url": "https://deine-domain.de/web/mods/mein-mod.jar",
"icon": "https://deine-domain.de/web/icon.png",
"rss": "https://deine-domain.de/web/rss.xml"
```
