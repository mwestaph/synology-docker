# Downloads

Docker Compose stack for download clients and VPN routing.

## Services

- Gluetun provides the VPN connection and network for qBittorrent.
- qBittorrent handles torrents.
- qBitrr coordinates qBittorrent with the media managers.
- SABnzbd handles Usenet downloads.

## Configuration

`compose.yaml` is a sanitized example of the stack. Copy `.env.example` to a private `.env` file and replace every example value before using Docker Compose. Keep the real `.env` out of GitHub. If deploying through Portainer, set the equivalent stack variables there.

The external Docker network `media_net` must already exist. qBitrr reads its private `config.toml` from the mounted appdata directory; that file is not included here. qBitrr and qBittorrent both mount the downloads directory at `/downloads` so their paths match.

The qBittorrent service also expects a private `discord-webhook.sh` file in its appdata `scripts` directory. Remove that bind mount if you do not use the script.
