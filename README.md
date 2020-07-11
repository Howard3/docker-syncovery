# Introduction
This is the unofficial Syncovery docker image, it's been compiled and prepared @ https://hub.docker.com/r/hlince/syncovery

# Usage
After accessing the interface the the user name is `default` and the password is `pass`.

# Docker-Compose Sample
The following sample is running against an unraid host. For other hosts it'll work the same but you'll likely want to change the mounts.

```
version: '2.2'
services:
  syncovery:
    cpu_shares: 256
    restart: unless-stopped
    image: hlince/syncovery
    volumes:
    - /mnt:/mnt
    - /boot:/boot
    - /mnt/user/appdata/syncovery:/config
    - /mnt/user/tmp/syncovery:/tmp
    ports:
    - 8999:8999
    - 8943:8943

```
Run Command docker-compose up -d
Go to http://your-docker-host:8999
Use the username default and the password pass

# Volume Mounts

You can mount any volumes you want to work with however this container needs one specific mount to store its configuration. Please mount a volume @ `/config` for persistent configuration. 
