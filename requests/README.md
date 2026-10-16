# Requests

Docker Compose stack for media requests, library maintenance, metadata, and notifications.

## Services

- Seerr
- Maintainerr
- Cleanarr
- Kometa
- Apprise
- A local Maintainerr to Apprise relay

## Configuration

`compose.yaml` uses a variable for Cleanarr's Plex token; other paths and IDs are written directly in the file. Copy `.env.example` to a private `.env` and set `PLEX_TOKEN`, or set it in Portainer. Keep real credentials and application configuration directories out of GitHub.

The external Docker network `media_net` must already exist. Compose creates the separate `requests_private` network for Apprise, Maintainerr, and the relay.

The relay uses the custom local image `media-maintainerr-apprise-relay`. Its source is not included here, so this stack cannot run as written on another host unless that image is built there. Maintainerr's user ID must have access to its data and media directories.

Apprise and Kometa have WUD digest watching and the local Docker update trigger enabled. The other services do not have an update trigger label in this Compose file. Apprise, Maintainerr, and the relay share `requests_private`; Cleanarr, Kometa, Maintainerr, and Seerr use the external `media_net` network.
