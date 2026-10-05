# Nextcloud

Docker Compose stack for self-hosted file storage and synchronization.

## Services

- Nextcloud
- PostgreSQL
- Redis

## Configuration

`compose.yaml` is a sanitized example of the current stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env`, database files, and Nextcloud data out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

Compose creates an internal `private` network for PostgreSQL and Redis and a separate `public` network for Nextcloud. The app's HTML, config, custom apps, and data directories have separate persistent mounts; keep those paths aligned with an existing installation when adapting this example.
