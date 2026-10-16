# Books

Docker Compose stack for managing and reading books, audiobooks, and comics.

## Services

- BookOrbit, backed by its own PostgreSQL/pgvector database
- Calibre
- Kapowarr
- Komga
- LazyLibrarian

## Configuration

`compose.yaml` includes BookOrbit and its `postgres` service. BookOrbit waits for a healthy database. The database is on the internal `bookorbit_private` network; BookOrbit also joins the external `media_net` network. Its application data, book library, and downloads are separate mounts. Set `BOOKORBIT_DB_PASSWORD` once for both containers, along with the JWT secret, setup token, and request encryption key. The app URL, library path, and user IDs are written directly in `compose.yaml`.

BookOrbit, Calibre, Kapowarr, Komga, and LazyLibrarian have WUD digest watching and the `docker.local` update trigger enabled. Confirm the Docker appdata backup and a nonempty dated BookOrbit database dump before relying on BookOrbit auto-updates.

Copy `.env.example` to a private `.env` and replace its four secret placeholders, or set those variables in Portainer. The Compose file covers all six services; `.env.example` lists only variables that file uses. Keep the real `.env` and application configuration directories out of GitHub.

The external Docker network `media_net` must already exist. Use the same host directories for books and comics across services so each service sees the same library files. Calibre's import path should point to the completed downloads directory.
