FROM ubuntu:latest

RUN apt-get update && apt-get install -y \
    software-properties-common \
    && add-apt-repository ppa:obsproject/obs-studio \
    && apt-get update \
    && apt-get install -y obs-studio xvfb vlc ffmpeg dbus-x11

RUN mkdir -p /root/.config/obs-studio

COPY global.ini /root/.config/obs-studio/global.ini
COPY ./basic /root/.config/obs-studio/basic

CMD xvfb-run obs