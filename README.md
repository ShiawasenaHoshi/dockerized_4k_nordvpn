Dockerized 4K Video Downloader + NordVPN
# Why?
The best youtube video downloader that I know is 4K Video Downloader. But there is a couple of issues:
- the downloader works only in window manager => not suited for servers
- the more channels you subscribed to, the sooner you get a captcha on youtube
Current project solves both issues.

# Features
- Easy installation and using
- Bypass video download restrictions using NordVPN
- 4k here doesn't need a window manager to use it, only docker
- WebUI access to 4k
- 4K updates to the newest version if you rebuild container

# Prerequisites
- NordVPN account is mandatory
- 4K VideoDownloader license is advantage

# Installation
1. copy ``.env.example`` to ``.env`` and add NordVPN credentials
2. ``sudo docker-compose up``
3. go to ``http://localhost:8887``
4. close actiona and configure 4k: add channels, license and etc
5. restart docker-compose

# Using your 4k-config
1. copy ``.env.example`` to ``.env`` and add NordVPN credentials
2. copy ``~/.config/4kdownload.com/4K Video Downloader.conf`` to project folder ``4k_data/config``. Check the ``locale`` is equal to nothing (== english locale)
```
locale=
```
3. start container until the moment 4k loads and then stop container
4. replace sqlite-database in ``4k_data/database`` with yours database from ``~/.local/share/4kdownload.com/4K Video Downloader/4K Video Downloader/``
5. restart docker-compose

# Todo
- configuration only with files (channels, license and etc) without moving the mouse
- 4k api: add channels, videos with get/post requests
- telegram bot
- the actiona script refactoring

# Thanks to
- [Doro Wu](https://github.com/fcwu) for [docker-ubuntu-vnc-desktop](https://github.com/fcwu/docker-ubuntu-vnc-desktop)
- [Jeroen](https://github.com/Joentje) for [NordVPN in docker](https://github.com/Joentje/nordvpn-proxy)
- Open Media OOO for [4K Video Downloader](https://www.4kdownload.com/)


