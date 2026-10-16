# WordPress

One Compose stack runs the El West and Michael WordPress sites, each with its own MariaDB service.

## Services

- `elwest-wordpress` and `elwest-mariadb`: port 8144, with an internal database network and a separate public network
- `michael-wordpress` and `michael-mariadb`: port 8145, on their own bridge network

## Configuration

The deployment file is `compose.yaml`. Copy `.env.example` to a private `.env`, set the database and root passwords, and use `docker compose up -d`; in Portainer, set the same stack variables there. `ELWEST_WORDPRESS_DB_PASSWORD` must equal `ELWEST_MARIADB_PASSWORD`. The Michael WordPress and MariaDB services both use `MICHAEL_WORDPRESS_DB_PASSWORD`.

The Michael site's `WP_HOME` and `WP_SITEURL` are set directly in `compose.yaml`, along with HTTPS handling for a reverse proxy. Database and site files are mounted from separate paths on `/volumeUSB1/usbshare`. Keep real passwords and application data out of GitHub.
