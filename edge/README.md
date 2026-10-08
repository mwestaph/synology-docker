Edge

Docker Compose stack for the Cloudflare Tunnel connector and Pi-hole DNS service.

## Services

- Cloudflared
- Pi-hole

## Configuration

`compose.yaml` is a sanitized example of the current stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and application configuration directories out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The stack creates a `public` Docker network. Cloudflared publishes its metrics endpoint on port 8082. Pi-hole publishes DNS on TCP and UDP port 53 and its web interface on port 8081. Limit access to these ports as appropriate for your network. Keep the persistent mount paths aligned with an existing installation when adapting this example.
