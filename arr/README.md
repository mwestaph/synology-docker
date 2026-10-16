# Arr

Media managers, indexers, subtitles, and related services.

## Services

- Bazarr: subtitles
- FlareSolverr: indexer challenge solving
- Lidarr: music
- NZBHydra2: Usenet indexer aggregation
- Prowlarr: indexer management
- Radarr: movies
- Sonarr: television
- Sportarr: sports

## Configuration

The current `compose.yaml` writes host paths, user IDs, and time zone directly; it does not use `.env` variables. Review those values before deploying to another host. The external `media_net` network must already exist. Keep media and downloads host paths consistent with the other stacks so imports resolve to the same files.

Bazarr, FlareSolverr, NZBHydra2, Prowlarr, Radarr, Sonarr, and Sportarr have WUD labels for the local Docker and SMTP triggers with a 24-hour watch delay. Sportarr also uses digest watching. Lidarr has no update trigger label in this Compose file. Keep application data and real credentials out of GitHub.
