# Nextcloud

Docker Compose stack for self-hosted file storage and synchronization.

## Services

- Nextcloud
- PostgreSQL
- Redis

## Configuration

`compose.yaml` uses `.env` variables for the database and admin passwords. Copy `.env.example` to a private `.env` and set both, or set them in Portainer. The admin username, host paths, and time zone are written directly in the Compose file. Keep real credentials, database files, and Nextcloud data out of GitHub.

Compose creates an internal `private` network for PostgreSQL and Redis and a separate `public` network for Nextcloud. The app's HTML, config, custom apps, and data directories have separate persistent mounts; keep those paths aligned with an existing installation when adapting this example. The Compose file pins the Nextcloud, PostgreSQL, and Redis images by digest. Major version changes need a separate application and database upgrade plan.
