WordPress

This directory contains a combined Compose file for both WordPress sites and separate examples for each site.

## Combined stack

`combined-compose.yaml` runs both WordPress sites and their MariaDB services. Copy this directory's `.env.example` to a private `.env`, replace the example passwords, and deploy with `docker compose -f combined-compose.yaml up -d`. In Portainer, set the same variables in the stack's environment variables instead.

The El West WordPress database password must equal `ELWEST_MARIADB_PASSWORD`. The Michael WordPress database password is shared with its MariaDB service. The Michael site URL is currently set directly in `combined-compose.yaml`.

## Separate examples

- `elwest/` — WordPress with a MariaDB service on an internal private network.
- `michael/` — WordPress with a MariaDB service and a configurable site URL.

Each directory has its own `compose.yaml` and `.env.example`. Copy the relevant example to a private `.env` and replace every example value before deploying. The separate `michael/` example uses `WORDPRESS_SITE_URL` to configure its domain.

Keep real passwords and application data out of GitHub.
