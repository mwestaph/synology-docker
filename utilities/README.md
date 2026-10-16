# Utilities

Monitoring, dashboards, duplicate-file management, and container update services.

## Services

- Beszel and Beszel Agent: system monitoring
- Dashdot: host dashboard
- dupeGuru: duplicate-file management
- Homarr: application dashboard
- Watchtower: updates for containers with its opt-in label
- WUD: image watching, SMTP notifications, and opt-in local Docker updates

## Configuration

Copy `.env.example` to a private `.env` and replace every example value, or set the variables in Portainer. Beszel Agent needs its hub key and token. Homarr needs an encryption key. Watchtower needs its notification address and SMTP app password. WUD needs its administrator and SMTP credentials. Keep credentials and application data out of GitHub.

Watchtower is scheduled for 3:30 a.m. `America/Los_Angeles` and only acts on containers labeled `com.centurylinklabs.watchtower.enable=true`. WUD's local watcher runs at 4:00 a.m. in the same time zone; its Docker trigger has `INCLUDEBYDEFAULT=false`, so only explicitly opted-in containers receive automatic updates. WUD also uses SMTP for notifications. The two updater services mount the Docker socket, so review their labels and schedules together.

Beszel, Beszel Agent, Dashdot, and dupeGuru have Watchtower opt-in labels. Homarr has a WUD local Docker trigger label. Dashdot, dupeGuru, and Homarr use the external `media_net` network; it must already exist. Beszel and WUD store their state under `/volumeUSB1/usbshare`, and Beszel Agent reads monitoring paths from both internal and USB storage.
