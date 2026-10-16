# Media Processing

Docker Compose stack for the media server, DVR recordings, file processing, and viewing statistics.

## Services

- Channels DVR
- FileFlows
- Plex
- Tautulli

## Configuration

The current `compose.yaml` writes host paths, user IDs, and time zone directly; it does not use `.env` variables. Review those values before redeploying or adapting the stack. Keep application configuration directories out of GitHub.

The external Docker network `media_net` must already exist. Channels DVR and Plex use host networking and `/dev/dri` for hardware access. FileFlows uses the host's Docker socket and a temporary directory that must exist on the host. Review those mounts and permissions before reusing this example.

Plex mounts the media directory at `/volume1/Plex` inside its container to preserve the current library paths. Its `/config` and `/transcode` mounts are separate. If your Plex libraries use another internal path, adjust that mount before deploying.

All four services have Watchtower opt-in labels. Tautulli also has WUD digest watching configured. Check the labels before changing automatic update behavior.
