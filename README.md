Make your
# Own studio
## for live streaming.
---
This repo aims to provide an easy setup to accept livestream input (like RTMP) from cameras, allow you to manipulate the video and stream it towards other platforms (another RTMP, yt, fb, twitch, etc.)

### Basic overview

```mermaid
erDiagram
    CAMERA_3 }|..|{ NGINX1_RTMP : push
    CAMERA_1 }|..|{ NGINX2_RTMP : push
    CAMERA_2 }|..|{ NGINX2_RTMP : push
    NGINX1_RTMP ||--o{ FFMPEG : modify
    NGINX2_RTMP ||--o{ OBS : pull
    FFMPEG ||--o{ OBS : pull
    STUDIO-UI ||--o{ OBS : "control"
    STUDIO-UI ||--o{ FFMPEG : "control"
    OBS ||--o{ YT : receives
    OBS ||--o{ FB : receives
    OBS ||--o{ RTMP_OUT : receives
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
