FROM nginx

RUN apt update \
    && apt purge -y nginx-* \
    && apt install -y nginx-extras libnginx-mod-rtmp

COPY rtmp.conf /etc/nginx/modules-enabled/
