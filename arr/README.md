Arr

Docker Compose stack for media management, indexing, subtitles, and related services.

## Services

- Bazarr
- FlareSolverr
- Lidarr
- NZBHydra2
- Prowlarr
- Radarr
- Sonarr
- Sportarr

## Configuration

`compose.yaml` is a sanitized example of the stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and the applications' `/config` directories out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The external Docker network `media_net` must already exist. The media and downloads variables must point to the same host directories used by the other stacks so container paths stay consistent.
