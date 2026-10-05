# Books

Docker Compose stack for managing and reading books, audiobooks, and comics. This example records the current setup and can be updated as the stack changes.

## Services

- Calibre
- Kapowarr
- Komga
- LazyLibrarian

## Configuration

`compose.yaml` is a sanitized example of the stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and application configuration directories out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The external Docker network `media_net` must already exist. Use the same host directories for books and comics across services so each service sees the same library files. Calibre's import path should point to the completed downloads directory.
