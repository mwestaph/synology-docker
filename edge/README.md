# Edge

Docker Compose stack for the Cloudflare Tunnel connector and Pi-hole DNS service.

## Services

- Cloudflared
- Pi-hole

## Configuration

`compose.yaml` is a sanitized example of the current stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and application configuration directories out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The stack creates a `public` Docker network. Cloudflared publishes its metrics endpoint on port 8082, has a Watchtower opt-in label, and has no persistent volume mount. Pi-hole publishes DNS on TCP and UDP port 53 and its web interface on port 8081. Its configuration is mounted from `/volume1/docker/appdata-recovery/edge/pihole`, following the USB recovery. Keep those mount paths aligned with the existing installation. Pi-hole is pinned to an image digest in `compose.yaml`.
