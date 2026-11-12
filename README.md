# DagIVMS

Video management system by DAGTECH INCORPORATED for commercial Hikvision and LTS camera sites.

DagIVMS gives operators one place to watch live video, search recordings and manage cameras across several recording servers and NVRs.

Status: early development. Not ready for production sites yet.

## How it is built

- `central_manager/` is the central server. It keeps the camera list, settings, users and the recording index in PostgreSQL. Video does not pass through it.
- `media_node/` runs close to the cameras. It pulls streams through MediaMTX, records selected cameras to local disks, talks to cameras over ONVIF and serves live and recorded video to clients.
- `nvr_client/` is the web client (React, TypeScript).
- `nvr_desktop/` is the Windows desktop client (PySide6, libmpv) for video walls.

## Planned for DagIVMS

- Hybrid recording: primary recording on site NVRs, backup recording of key cameras on media nodes.
- Hikvision and LTS NVR integration over ISAPI: channels, recording search, playback and events.
- Security: node enrollment tokens, authenticated node APIs and streams, encrypted camera credentials, HTTPS, built-in users and roles.
- Linux deployment with Docker Compose, backups and monitoring.

## License

MIT, see `LICENSE`. Third-party notices are in `THIRD_PARTY_LICENSES`.
