# Books

Docker Compose stack for managing and reading books, audiobooks, and comics.

## Services

- BookOrbit, backed by its own PostgreSQL/pgvector database
- Calibre
- Kapowarr
- Komga
- LazyLibrarian

## Configuration

The running Portainer stack includes BookOrbit and its `postgres` service. BookOrbit waits for a healthy database, keeps its database on the internal `bookorbit_private` network, and also joins `media_net` to reach other services. Its application data, book library, and downloads are separate mounts. The database password must have the same value in both services. Set `BOOKORBIT_DB_PASSWORD`, `BOOKORBIT_JWT_SECRET`, `BOOKORBIT_SETUP_BOOTSTRAP_TOKEN`, and `BOOKORBIT_REQUEST_ENCRYPTION_KEY` privately in Portainer.

BookOrbit, Calibre, Kapowarr, Komga, and LazyLibrarian have WUD digest watching and the `docker.local` update trigger enabled. Confirm the Docker appdata backup and a nonempty dated BookOrbit database dump before relying on BookOrbit auto-updates.

The checked-in `compose.yaml` and `.env.example` are still sanitized examples of the four older services; they do not yet include BookOrbit or the current WUD labels. Update them from the running Portainer stack before using this repository to redeploy Books. Keep the real `.env` and application configuration directories out of GitHub.

The external Docker network `media_net` must already exist. Use the same host directories for books and comics across services so each service sees the same library files. Calibre's import path should point to the completed downloads directory.
