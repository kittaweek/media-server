# media-server

Media server with Jellyfin

### Setup

1. Setup .env file

```bash
# Check UID/GID of user for environment
id ${USERNAME}
```

2. Mount media drive

```sh
# Check drive
lsblk

# Mount
sudo mount -o ro -t ntfs-3g ${SOURCE_PATH} ${DIRECTORY_PATH}

# change ownership
chown ${USERNAME} ${SOURCE_PATH}
```

3. Startup Jellyfin

```sh
# Docker
docker-compose up -d
```

### Remove Setup

```sh

# Unmount
docker-compose down

sudo umount ${DIRECTORY_PATH}

```
