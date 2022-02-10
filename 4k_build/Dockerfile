FROM dorowu/ubuntu-desktop-lxde-vnc:latest

WORKDIR /home/desktopuser
RUN mkdir -p .config/4kdownload.com/ \
    && mkdir -p .local/share/4kdownload.com/4K Video Downloader/4K Video Downloader/ \
    && mkdir -p  Videos/4K Video Downloader \
    && curl -i -s -k -X 'GET' -H 'Host: www.4kdownload.com' -b 'prefer_user_os=ubuntu; prefer_user_os_arch=x64' 'https://www.4kdownload.com/thanks-for-downloading?source=videodownloader' | egrep -oh "(https://dl.4kdownload.com/app/4kvideodownloader.+?.deb)" | head -1 | xargs wget -O 4k.deb \
    && dpkg -i 4k.deb \
    && rm -rf 4k.deb

# Install required package
RUN apt update \
    && apt install -y --no-install-recommends libqt5x11extras5 actiona \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/*

HEALTHCHECK --interval=5s --timeout=5s --retries=6 --start-period=60s CMD ((curl --fail http://127.0.0.1:6079/api/health) && (ifconfig | grep tun >/dev/null)) || exit 1
