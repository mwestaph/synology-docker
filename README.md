# Synology Docker

Docker Compose configurations and deployment notes for the Synology home lab.

| Stack | What it runs |
| --- | --- |
| [Arr](arr/README.md) | Media managers, indexers, subtitles, and FlareSolverr |
| [Books](books/README.md) | BookOrbit and its database, Calibre, Kapowarr, Komga, and LazyLibrarian |
| [Downloads](downloads/README.md) | Gluetun, qBittorrent, qBitrr, and SABnzbd |
| [Edge](edge/README.md) | Cloudflare Tunnel and Pi-hole DNS |
| [Linkwarden](linkwarden/README.md) | Linkwarden and PostgreSQL |
| [Media Processing](media-processing/README.md) | Plex, Channels DVR, FileFlows, and Tautulli |
| [Nextcloud](nextcloud/README.md) | Nextcloud, PostgreSQL, and Redis |
| [Requests](requests/README.md) | Seerr, Maintainerr, Cleanarr, Kometa, Apprise, and the notification relay |
| [Utilities](utilities/README.md) | Beszel, Dashdot, dupeGuru, Homarr, Watchtower, and WUD |
| [WordPress](wordpress/README.md) | Two WordPress sites with separate MariaDB services |

Each stack has a `compose.yaml`, a `.env.example`, and a README with its dependencies. Use a private `.env` or Portainer stack variables for settings referenced as `${VARIABLE}`. Many NAS paths and user IDs are written directly in the Compose files; review them before deploying to another host. Do not commit credentials or application data. The external `media_net` network must exist before deploying stacks that use it.

Editing these files in GitHub does not redeploy the running Portainer stacks.
