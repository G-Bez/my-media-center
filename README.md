# MY MEDIA CENTER
Docker stack portable media server built with docker compose, including:

- [linuxserver/jellyfin](https://docs.linuxserver.io/images/docker-jellyfin/) as media player.
- [linuxserver/sonarr](https://docs.linuxserver.io/images/docker-sonarr/?h=sonarr) as tv series collection manager.
- [linuxserver/radarr](https://docs.linuxserver.io/images/docker-radarr/?h=radarr) as movie collection manager.
- [linuxserver/lidarr](https://docs.linuxserver.io/images/docker-lidarr/?h=lidarr) as music collection manager.
- [linuxserver/prowlarr](https://docs.linuxserver.io/images/docker-prowlarr/?h=prowlarr) as indexer manager.
- [linuxserver/qbittorrent](https://docs.linuxserver.io/images/docker-qbittorrent/?h=qbittorrent) as torrent client.
- [linuxserver/speedtest-tracker](https://docs.linuxserver.io/images/docker-speedtest-tracker/?h=speedtest+tracker) as network speedtest tracker.
- [gethomepage/homepage](https://gethomepage.dev/latest/) as server dashboard.
- [Optional] [jc21/nginx-proxy-manager](https://nginxproxymanager.com/) as reverse proxy.

# SETUP
1) Pull the repository.
2) Use the example environment file `.env.example` as a template for setting up your environment variables. Jellyfin, Lidarr, Radarr and Sonarr API key can be retrieved by accessing the related services. Speedtest-tracker and qBittorent provide default user credentials on the first startup. Find the speedtest ones [here](https://docs.speedtest-tracker.dev/security/authentication), and the qBittorent ones on its container log. Replace these credentials with your own as soon as possible, and set them in your `.env`.
3) Build the stack by opening the terminal and typing:

    ```
    cd path/to/repository
    docker compose up -d
    ```

4) Log into your services and link them via in-app settings (Link Jellyfin to Lidarr-Radarr-Sonarr, Prowlarr to Lidarr-Radarr-Sonarr and qBittorrent). 

[Optional] Enable NGINX proxy manager service, get a domain name (or a DDNS subdomain) and set your reverse proxy.

