Requests

Docker Compose stack for media requests, library maintenance, metadata, and notifications.

## Services

- Seerr
- Maintainerr
- Cleanarr
- Kometa
- Apprise
- A local Maintainerr to Apprise relay

## Configuration

`compose.yaml` is a sanitized example of the stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` and application configuration directories out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The external Docker network `media_net` must already exist. Compose creates the separate `requests_private` network for Apprise, Maintainerr, and the relay.

The relay uses the custom local image `media-maintainerr-apprise-relay`. Its source is not included here, so this stack cannot run as written on another host unless that image is built there. Maintainerr's user ID must have access to its data and media directories.
