# Linkwarden

Docker Compose stack for self-hosted bookmark management and archiving.

## Services

- Linkwarden
- PostgreSQL

## Configuration

`compose.yaml` is a sanitized example of the current stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and database files out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The password embedded in `DATABASE_URL` must match `POSTGRES_PASSWORD`. URL-encode reserved characters in the URL password. `NEXTAUTH_URL` must be the URL used to access Linkwarden. Compose creates the internal `private` network for the database and a separate `public` network for Linkwarden.
