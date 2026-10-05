# Media Processing

Docker Compose stack for the media server, DVR recordings, file processing, and viewing statistics.

## Services

- Channels DVR
- FileFlows
- Plex
- Tautulli

## Configuration

`compose.yaml` is a sanitized example of the current stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and application configuration directories out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The external Docker network `media_net` must already exist. Channels DVR and Plex use host networking and `/dev/dri` for hardware access. FileFlows uses the host's Docker socket and a temporary directory that must exist on the host. Review those mounts and permissions before reusing this example.

Plex mounts the media directory at `/volume1/Plex` inside its container to preserve the current library paths. If your Plex libraries use another internal path, adjust that mount before deploying.
