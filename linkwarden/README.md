# Linkwarden

Docker Compose stack for self-hosted bookmark management and archiving.

## Services

- Linkwarden
- PostgreSQL

## Configuration

`compose.yaml` is a sanitized example of the current stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and database files out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

`NEXTAUTH_URL` must be the URL used to access Linkwarden. Compose creates an internal `private` network for PostgreSQL and a separate `public` network for Linkwarden. Linkwarden has a WUD local Docker trigger label; PostgreSQL does not.

`POSTGRES_PASSWORD` supplies the password for both PostgreSQL and Linkwarden's `DATABASE_URL`. Keep the real value private and use a URL-safe value because Compose inserts it into a connection URL. The password previously embedded in this repository remains in Git history; changing this file does not rotate the running database password. Changing `POSTGRES_PASSWORD` alone also does not change a password already stored in PostgreSQL's data directory.
