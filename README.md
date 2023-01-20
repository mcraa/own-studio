Make your
# Own studio
## for live streaming.
---
This repo aims to provide an easy setup to accept livestream input (like RTMP) from cameras, allow you to manipulate the video and stream it towards other platforms (another RTMP, yt, fb, twitch, etc.)

### Basic overview

```mermaid
erDiagram
    CAMERA_3 }|..|{ NGINX_RTMP1 : push
    CAMERA_1 }|..|{ NGINX_RTMP2 : push
    CAMERA_2 }|..|{ NGINX_RTMP2 : push
    NGINX_RTMP1 ||--o{ OBS : pull
    NGINX_RTMP2 ||--o{ OBS : pull
    STUDIO-UI ||--|| OBS : "control"
    OBS ||--|| NGINX_OUT : push
    NGINX_OUT ||--o| YT : receives
    NGINX_OUT ||--o| FB : receives
    NGINX_OUT ||--o| RTMP_OUT : receives
```

### Usage

```shell
docker compose up -d
```

1. Navigate to http://localhost:5000/
2. Connect to the OBS Studio:

| | |
|---|---|
|URL|ws://localhost:4455|
|Password|abc123|

You can change the OBS Studio password in `global.ini` (or disable it) before starting containers.
