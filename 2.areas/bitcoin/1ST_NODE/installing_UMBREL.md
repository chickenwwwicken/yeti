## Download Info
``` bash
 curl -L https://umbrel.sh | bash
```


``` bash
About to install Umbrel in "/home/s0f7f0rk/umbrel".
If you would like to install somewhere else you can specify a custom location with:

  curl -L https://umbrel.sh | bash -s -- --install-path /some/path

Waiting for 10 seconds...

You may press Ctrl+C now to abort the install.
```

``` shell
The following additional packages will be installed:
  libjq1 libonig5
The following NEW packages will be installed:
  fswatch jq libjq1 libonig5
```

``` shell
The following additional packages will be installed:
  adwaita-icon-theme at-spi2-core dconf-gsettings-backend dconf-service fontconfig fontconfig-config fonts-dejavu-core
  gir1.2-atk-1.0 gir1.2-freedesktop gir1.2-gdkpixbuf-2.0 gir1.2-gtk-3.0 gir1.2-harfbuzz-0.0 gir1.2-pango-1.0
  gsettings-desktop-schemas gtk-update-icon-cache hicolor-icon-theme humanity-icon-theme libatk-bridge2.0-0
  libatk1.0-0 libatk1.0-data libatspi2.0-0 libavahi-client3 libavahi-common-data libavahi-common3 libavahi-core7
  libcairo-gobject2 libcairo2 libcolord2 libcups2 libdaemon0 libdatrie1 libdconf1 libdeflate0 libepoxy0 libfontconfig1
  libfreetype6 libgdk-pixbuf-2.0-0 libgdk-pixbuf2.0-bin libgdk-pixbuf2.0-common libgraphite2-3 libgtk-3-0 libgtk-3-bin
  libgtk-3-common libharfbuzz0b libjbig0 libjpeg-turbo8 libjpeg8 liblcms2-2 libpango-1.0-0 libpangocairo-1.0-0
  libpangoft2-1.0-0 libpangoxft-1.0-0 libpixman-1-0 librsvg2-2 librsvg2-common libthai-data libthai0 libtiff5
  libwayland-client0 libwayland-cursor0 libwayland-egl1 libwebp7 libxcb-render0 libxcb-shm0 libxcomposite1 libxcursor1
  libxdamage1 libxfixes3 libxft2 libxi6 libxinerama1 libxkbcommon0 libxrandr2 libxrender1 libxtst6 python3-avahi
  session-migration ubuntu-mono
Suggested packages:
  avahi-autoipd colord cups-common gvfs liblcms2-utils avahi-autoipd | zeroconf librsvg2-bin
The following NEW packages will be installed:
  adwaita-icon-theme at-spi2-core avahi-daemon avahi-discover dconf-gsettings-backend dconf-service fontconfig
  fontconfig-config fonts-dejavu-core gir1.2-atk-1.0 gir1.2-freedesktop gir1.2-gdkpixbuf-2.0 gir1.2-gtk-3.0
  gir1.2-harfbuzz-0.0 gir1.2-pango-1.0 gsettings-desktop-schemas gtk-update-icon-cache hicolor-icon-theme
  humanity-icon-theme libatk-bridge2.0-0 libatk1.0-0 libatk1.0-data libatspi2.0-0 libavahi-client3
  libavahi-common-data libavahi-common3 libavahi-core7 libcairo-gobject2 libcairo2 libcolord2 libcups2 libdaemon0
  libdatrie1 libdconf1 libdeflate0 libepoxy0 libfontconfig1 libfreetype6 libgdk-pixbuf-2.0-0 libgdk-pixbuf2.0-bin
  libgdk-pixbuf2.0-common libgraphite2-3 libgtk-3-0 libgtk-3-bin libgtk-3-common libharfbuzz0b libjbig0 libjpeg-turbo8
  libjpeg8 liblcms2-2 libnss-mdns libpango-1.0-0 libpangocairo-1.0-0 libpangoft2-1.0-0 libpangoxft-1.0-0 libpixman-1-0
  librsvg2-2 librsvg2-common libthai-data libthai0 libtiff5 libwayland-client0 libwayland-cursor0 libwayland-egl1
  libwebp7 libxcb-render0 libxcb-shm0 libxcomposite1 libxcursor1 libxdamage1 libxfixes3 libxft2 libxi6 libxinerama1
  libxkbcommon0 libxrandr2 libxrender1 libxtst6 python3-avahi session-migration ubuntu-mono
0 upgraded, 81 newly installed, 0 to remove and 40 not upgraded.
```

## DOCKER
```
WSL DETECTED: We recommend using Docker Desktop for Windows.
Please get Docker Desktop from https://www.docker.com/products/docker-desktop/


You may press Ctrl+C now to abort this script.
+ sleep 20
+ sh -c apt-get update -qq >/dev/null
+ sh -c DEBIAN_FRONTEND=noninteractive apt-get install -y -qq apt-transport-https ca-certificates curl >/dev/null
+ sh -c install -m 0755 -d /etc/apt/keyrings
+ sh -c curl -fsSL "https://download.docker.com/linux/ubuntu/gpg" | gpg --dearmor --yes -o /etc/apt/keyrings/docker.gpg
+ sh -c chmod a+r /etc/apt/keyrings/docker.gpg
+ sh -c echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu jammy stable" > /etc/apt/sources.list.d/docker.list
+ sh -c apt-get update -qq >/dev/null
+ sh -c DEBIAN_FRONTEND=noninteractive apt-get install -y -qq docker-ce docker-ce-cli containerd.io docker-compose-plugin docker-ce-rootless-extras docker-buildx-plugin >/dev/null
+ sh -c docker version
Client: Docker Engine - Community
 Version:           26.0.0
 API version:       1.45
 Go version:        go1.21.8
 Git commit:        2ae903e
 Built:             Wed Mar 20 15:17:48 2024
 OS/Arch:           linux/amd64
 Context:           default

Server: Docker Engine - Community
 Engine:
  Version:          26.0.0
  API version:      1.45 (minimum version 1.24)
  Go version:       go1.21.8
  Git commit:       8b79278
  Built:            Wed Mar 20 15:17:48 2024
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.6.28
  GitCommit:        ae07eda36dd25f8a1b98dfbf587313b99c0190bb
 runc:
  Version:          1.1.12
  GitCommit:        v1.1.12-0-g51d5e94
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0

================================================================================

To run Docker as a non-privileged user, consider setting up the
Docker daemon in rootless mode for your user:

    dockerd-rootless-setuptool.sh install

Visit https://docs.docker.com/go/rootless/ to learn about rootless mode.


To run the Docker daemon as a fully privileged service, but granting non-root
users access, refer to https://docs.docker.com/go/daemon-access/

WARNING: Access to the remote API on a privileged Docker daemon is equivalent
         to root access on the host. Refer to the 'Docker daemon attack surface'
         documentation for details: https://docs.docker.com/go/attack-surface/

================================================================================
```

## PYTHON
```
The following additional packages will be installed:
  python3-attr python3-certifi python3-chardet python3-distutils python3-docker python3-dockerpty python3-docopt
  python3-dotenv python3-idna python3-jsonschema python3-lib2to3 python3-pyrsistent python3-requests
  python3-setuptools python3-texttable python3-urllib3 python3-websocket
Suggested packages:
  python-attr-doc python-jsonschema-doc python3-openssl python3-socks python-requests-doc python-setuptools-doc
Recommended packages:
  docker.io
The following NEW packages will be installed:
  docker-compose libffi-dev python3-attr python3-certifi python3-chardet python3-distutils python3-docker
  python3-dockerpty python3-docopt python3-dotenv python3-idna python3-jsonschema python3-lib2to3 python3-pyrsistent
  python3-requests python3-setuptools python3-texttable python3-urllib3 python3-websocket
0 upgraded, 19 newly installed, 0 to remove and 40 not upgraded.
```

## UMBREL CONFIG
```
[Service]
Type=forking
TimeoutStartSec=infinity
TimeoutStopSec=16min
ExecStart=/home/s0f7f0rk/umbrel/scripts/start
ExecStop=/home/s0f7f0rk/umbrel/scripts/stop
User=root
Group=root
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=umbrel startup
RemainAfterExit=yes
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target
Created symlink /etc/systemd/system/multi-user.target.wants/umbrel-startup.service → /etc/systemd/system/umbrel-startup.service.
Skipping status update when not on Umbrel OS

======================================
============ CONFIGURING =============
=============== UMBREL ===============
======================================

Generating auth credentials

Generating Tor password

Unable to find image 'getumbrel/tor:0.4.7.8@sha256:2ace83f22501f58857fa9b403009f595137fa2e7986c4fda79d82a8119072b6a' locally
docker.io/getumbrel/tor@sha256:2ace83f22501f58857fa9b403009f595137fa2e7986c4fda79d82a8119072b6a: Pulling from getumbrel/tor
461246efe0a7: Pull complete
c8bc27c5e55c: Pull complete
472ce9feeded: Pull complete
Digest: sha256:2ace83f22501f58857fa9b403009f595137fa2e7986c4fda79d82a8119072b6a
Status: Downloaded newer image for getumbrel/tor@sha256:2ace83f22501f58857fa9b403009f595137fa2e7986c4fda79d82a8119072b6a
Configuring permissions...
```

## START
``` 
Configuration successful
You can now start Umbrel by running:
  sudo ./scripts/start
```

## FINAL
```
Umbrel is now accessible at
  http://DESKTOP-DGRQ1C2.local
  http://172.31.231.13
Skipping status update when not on Umbrel OS

Umbrel has been sucessfully installed!
```
