# WordPress

Two separate WordPress and MariaDB stacks. These sanitized examples record the current setup and can be updated independently.

## Stacks

- `elwest/` — WordPress with a MariaDB service on an internal private network.
- `michael/` — WordPress with a MariaDB service and a configurable site URL.

Each directory contains its own `compose.yaml` and `.env.example`. Copy the relevant `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep real passwords and application data out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The WordPress database password must match the MariaDB user password in each stack. The `michael` example uses `WORDPRESS_SITE_URL` so the real domain does not need to appear in this public repository.
