# Linkwarden

Docker Compose stack for self-hosted bookmark management and archiving.

## Services

- Linkwarden
- PostgreSQL

## Configuration

`compose.yaml` is a sanitized example of the current stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and database files out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

`NEXTAUTH_URL` must be the URL used to access Linkwarden. Compose creates an internal `private` network for PostgreSQL and a separate `public` network for Linkwarden. Linkwarden has a WUD local Docker trigger label; PostgreSQL does not.

**Credential mismatch to resolve before redeploying:** `compose.yaml` currently embeds the database credential in `DATABASE_URL`, while the PostgreSQL service reads `POSTGRES_PASSWORD` from the environment. Those values must match. Changing `POSTGRES_PASSWORD` alone will not change Linkwarden's connection string. The Compose file is left unchanged here.
